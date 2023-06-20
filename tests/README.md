# 自述测试（草稿）

## 集成测试

### 准备工作

该存储库包含了针对多个搜索引擎和数据库的功能测试。这些测试旨在验证引擎和数据库根据其规范和要求的正确行为。

要运行一些集成测试，例如位于`tests/integration_tests/vectorstores/`目录中的测试，您需要安装以下软件：

- Docker
- Python 3.8.1 或更高版本

在 `pyproject.toml` 文件中，我们有一个可选的组 `test_integration`。这个组应该包含用于集成测试的依赖项，并可以使用以下命令进行安装：

```bash
poetry install --with test_integration
```

任何新的依赖项都应通过运行以下命令来添加：

```bash
# add package and install it after adding:
poetry add tiktoken@latest --group "test_integration" && poetry install --with test_integration
```

在运行任何测试之前，您应该启动一个具有所有必要依赖项的特定Docker容器。例如，我们在`test_elasticsearch.py`中使用`elasticsearch.yml`容器。

```bash
cd tests/integration_tests/vectorstores/docker-compose
docker-compose -f elasticsearch.yml up
```

### 准备本地测试环境变量：

- 将 `tests/.env.example` 复制到 `tests/.env`
- 在 `tests/.env` 文件中设置变量，例如 `OPENAI_API_KEY`

另外，需要注意的是，某些集成测试可能需要设置特定的环境变量，例如 `OPENAI_API_KEY`。在运行测试之前，请确保设置了所需的环境变量，以确保测试能够正确执行。

### 使用 pytest-vcr 记录 HTTP 交互

该存储库中的一些集成测试涉及向外部服务发出HTTP请求。为了防止这些请求在每次运行测试时被执行，我们使用pytest-vcr来记录和重放HTTP交互。

在CI/CD流水线中运行测试时，您可能不希望修改现有的记录。您可以使用--vcr-record=none命令行选项来禁用记录新的记录。以下是一个示例：

```bash
pytest --log-cli-level=10 tests/integration_tests/vectorstores/test_pinecone.py --vcr-record=none
pytest tests/integration_tests/vectorstores/test_elasticsearch.py --vcr-record=none

```

### 运行一些带有覆盖率的测试:

```bash
pytest tests/integration_tests/vectorstores/test_elasticsearch.py --cov=langchain --cov-report=html
start "" htmlcov/index.html || open htmlcov/index.html

```