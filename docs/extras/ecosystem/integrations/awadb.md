# AwaDB

>[AwaDB](https://github.com/awa-ai/awadb)是用于LLM应用程序的嵌入向量的搜索和存储的AI原生数据库。

## 安装和设置

```bash
pip install awadb
```


## VectorStore

有一个围绕AwaDB向量数据库的包装器，可以让您将其用作向量存储，无论是用于语义搜索还是示例选择。

```python
from langchain.vectorstores import AwaDB
```

有关AwaDB封装程序的更详细演示，请参阅[此笔记本](../modules/indexes/vectorstores/examples/awadb.ipynb)。
