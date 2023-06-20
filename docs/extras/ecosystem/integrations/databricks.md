Databricks
==========

[Databricks](https://www.databricks.com/) Lakehouse平台将数据、分析和人工智能统一在一个平台上。

Databricks以多种方式支持LangChain生态系统：

1. SQLDatabase Chain的Databricks连接器：SQLDatabase.from_databricks()提供了通过LangChain在Databricks上查询数据的简便方法
2. Databricks管理的MLflow与LangChain集成：使用更少的步骤跟踪和提供LangChain应用程序
3. Databricks作为LLM提供者：通过服务端点或集群驱动程序代理应用程序在Databricks上部署经过优化的LLM，并通过langchain.llms.Databricks进行查询。
4. Databricks Dolly：Databricks开源了Dolly，可以用于商业用途，并可通过Hugging Face Hub访问。

SQLDatabase Chain的Databricks连接器
----------------------------------------------
您可以使用LangChain的SQLDatabase包装器连接到[Databricks运行时](https://docs.databricks.com/runtime/index.html)和[Databricks SQL](https://www.databricks.com/product/databricks-sql)。有关详细信息，请参阅笔记本[Connect to Databricks](./databricks/databricks.html)。

Databricks管理的MLflow与LangChain集成。

MLflow是一个开源平台，用于管理机器学习生命周期，包括实验、可重现性、部署和中央模型注册。有关MLflow与LangChain集成的详细信息，请参阅笔记本[MLflow回调处理程序](./mlflow_tracking.ipynb)。

Databricks提供了一个完全托管和托管的MLflow版本，集成了企业安全功能、高可用性和其他Databricks工作区功能，例如实验和运行管理以及笔记本修订捕获。Databricks上的MLflow为跟踪和保护机器学习模型训练运行以及运行机器学习项目提供了集成的体验。详情请参阅[MLflow指南](https://docs.databricks.com/mlflow/index.html)。

Databricks托管的MLflow使得在Databricks上开发LangChain应用程序更加方便。对于MLflow跟踪，您不需要设置跟踪URI。对于MLflow模型服务，您可以将LangChain Chains保存为MLflow langchain flavor，并在Databricks上用几次点击即可注册和服务这个Chain，凭据由MLflow模型服务安全管理。

Databricks作为LLM提供商
-------------------------

笔记本[将Databricks端点包装为LLMs](../modules/models/llms/integrations/databricks.html)演示了在LangChain中将Databricks端点包装为LLMs的方法。它支持两种类型的端点：服务端点，推荐用于生产和开发；集群驱动程序代理应用程序，推荐用于交互式开发。 

Databricks端点支持Dolly，但也非常适合托管MPT-7B或Hugging Face生态系统中的任何其他模型。Databricks端点还可以与OpenAI等专有模型一起使用，为企业提供治理层。

Databricks Dolly
----------------

Databricks的Dolly是一个在Databricks机器学习平台上训练的遵循指令的大型语言模型，可用于商业用途。该模型在Hugging Face Hub上以databricks/dolly-v2-12b的形式提供。请参阅笔记本[Hugging Face Hub](../modules/models/llms/integrations/huggingface_hub.html)以了解如何通过与LangChain集成的Hugging Face Hub访问该模型的说明。 
