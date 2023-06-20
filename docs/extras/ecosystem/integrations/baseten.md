# Baseten

了解如何在 Baseten 上使用 LangChain 模型。

## 安装和设置

- 创建一个 [Baseten](https://baseten.co) 账户和 [API 密钥](https://docs.baseten.co/settings/api-keys)。
- 使用 `pip install baseten` 安装 Baseten Python 客户端。
- 使用您的 API 密钥进行身份验证 `baseten login`

## 调用模型

Baseten通过LLM模块与LangChain集成，该模块为在您的Baseten工作区上部署的模型提供了一个标准化且可互操作的接口。

您可以通过[Baseten模型库](https://app.baseten.co/explore/)一键部署基础模型，如WizardLM和Alpaca，或者如果您有自己的模型，可以使用[此教程](https://docs.baseten.co/deploying-models/deploy)进行部署。

在这个示例中，我们将使用WizardLM。[在这里部署WizardLM](https://app.baseten.co/explore/wizardlm)，并跟随已部署模型的[版本ID](https://docs.baseten.co/managing-models/manage)进行操作。

```python
from langchain.llms import Baseten

wizardlm = Baseten(model="MODEL_VERSION_ID", verbose=True)

wizardlm("What is the difference between a Wizard and a Sorcerer?")
```
