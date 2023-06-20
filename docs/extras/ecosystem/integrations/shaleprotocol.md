# Shale协议

[Shale协议](https://shaleprotocol.com)提供了用于开放LLMs的可投入生产的推理API。由于它托管在高度可扩展的GPU云基础设施上，因此它是一个即插即用的API。

我们的免费套餐支持每个密钥每天最多1K个请求，因为我们希望消除任何人开始使用LLMs构建genAI应用程序的障碍。

使用Shale协议，开发人员/研究人员可以免费创建应用程序并探索开放LLMs的功能。

本页面介绍了如何将Shale-Serve API与LangChain集成。

截至2023年6月，默认情况下，API支持Vicuna-13B。我们将在未来的版本中支持更多的LLMs，例如Falcon-40B。


## 如何操作

### 1. 在https://shaleprotocol.com上找到我们的Discord链接。通过我们的Discord上的"Shale Bot"生成一个API密钥。不需要信用卡，也没有免费试用。这是一个永久免费的层，每个API密钥每天限制为1K。

### 2. 使用 https://shale.live/v1 作为 OpenAI API 的替代方案

例如
```python
from langchain.llms import OpenAI
from langchain import PromptTemplate, LLMChain

import os
os.environ['OPENAI_API_BASE'] = "https://shale.live/v1"
os.environ['OPENAI_API_KEY'] = "ENTER YOUR API KEY"

llm = OpenAI()

template = """Question: {question}

# Answer: Let's think step by step."""

prompt = PromptTemplate(template=template, input_variables=["question"])

llm_chain = LLMChain(prompt=prompt, llm=llm)

question = "What NFL team won the Super Bowl in the year Justin Beiber was born?"

llm_chain.run(question)

```
