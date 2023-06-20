# 🦜️🔗 LangChain

⚡ 通过可组合性构建LLM应用程序 ⚡

[![发布说明](https://img.shields.io/github/release/hwchase17/langchain)](https://github.com/hwchase17/langchain/releases)
[![lint](https://github.com/hwchase17/langchain/actions/workflows/lint.yml/badge.svg)](https://github.com/hwchase17/langchain/actions/workflows/lint.yml)
[![测试](https://github.com/hwchase17/langchain/actions/workflows/test.yml/badge.svg)](https://github.com/hwchase17/langchain/actions/workflows/test.yml)
[![下载量](https://static.pepy.tech/badge/langchain/month)](https://pepy.tech/project/langchain)
[![许可证: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Twitter](https://img.shields.io/twitter/url/https/twitter.com/langchainai.svg?style=social&label=关注%20%40LangChainAI)](https://twitter.com/langchainai)
[![](https://dcbadge.vercel.app/api/server/6adMQxSpJS?compact=true&style=flat)](https://discord.gg/6adMQxSpJS)
[![在 Dev Containers 中打开](https://img.shields.io/static/v1?label=Dev%20Containers&message=打开&color=blue&logo=visualstudiocode)](https://vscode.dev/redirect?url=vscode://ms-vscode-remote.remote-containers/cloneInVolume?url=https://github.com/hwchase17/langchain)
[![在 GitHub Codespaces 中打开](https://github.com/codespaces/badge.svg)](https://codespaces.new/hwchase17/langchain)
[![GitHub star chart](https://img.shields.io/github/stars/hwchase17/langchain?style=social)](https://star-history.com/#hwchase17/langchain)
[![Dependency Status](https://img.shields.io/librariesio/github/hwchase17/langchain)](https://libraries.io/github/hwchase17/langchain)
[![Open Issues](https://img.shields.io/github/issues-raw/hwchase17/langchain)](https://github.com/hwchase17/langchain/issues)


寻找JS/TS版本？请查看[LangChain.js](https://github.com/hwchase17/langchainjs)。

**生产支持：** 当您将LangChains投入生产时，我们将提供更全面的支持。请填写[此表格](https://forms.gle/57d8AmXBYp8PP8tZA)，我们将为您设置一个专门的支持Slack频道。

## 快速安装

`pip install langchain`
或者
`conda install langchain -c conda-forge`

## 🤔 这是什么？

大型语言模型（LLM）正在成为一种具有变革性的技术，使开发人员能够构建以前无法实现的应用程序。然而，仅仅使用这些LLM往往不足以创建一个真正强大的应用程序 - 真正的力量在于将它们与其他计算或知识源结合起来。

本库旨在帮助开发这些类型的应用程序。这些应用程序的常见示例包括：

**❓ 在特定文档上的问答**

- [文档](https://python.langchain.com/docs/use_cases/question_answering/)
- 端到端示例：[在Notion数据库上的问答](https://github.com/hwchase17/notion-qa)

**💬 聊天机器人**

- [文档](https://python.langchain.com/docs/use_cases/chatbots/)
- 端到端示例：[Chat-LangChain](https://github.com/hwchase17/chat-langchain)

**🤖 代理程序**

- [文档](https://python.langchain.com/docs/modules/agents/)
- 端到端示例：[GPT+WolframAlpha](https://huggingface.co/spaces/JavaFXpert/Chat-GPT-LangChain)

## 📖 文档

请参阅[此处](https://python.langchain.com)获取有关以下内容的完整文档：

- 入门指南（安装、环境设置、简单示例）
- 如何示例（演示、集成、辅助函数）
- 参考（完整的API文档）
- 资源（核心概念的高级解释）

## 🚀 这可以帮助解决什么问题？

LangChain的设计目标主要有六个主要领域。
按照复杂性递增的顺序，它们包括：

**📃 LLMs和Prompts：**

这包括prompt管理，prompt优化，适用于所有LLMs的通用接口以及与LLMs一起使用的常用工具。

**🔗 链：**

链不仅限于单个LLM调用，还涉及到一系列的调用（无论是对LLM还是其他实用程序的调用）。LangChain提供了一种标准的链式接口，与其他工具有很多的集成，并提供了常见应用程序的端到端链。

**📚 数据增强生成：**

数据增强生成涉及特定类型的链，首先与外部数据源进行交互，以获取用于生成步骤的数据。示例包括对长文本进行摘要和在特定数据源上进行问题/回答。

**🤖 代理人：**

**👥 代理人:**

代理人涉及使用LLM（语言模型）做出决策，选择要采取的行动，观察结果，并重复此过程直到完成。LangChain为代理人提供了一个标准接口，并提供了一系列可供选择的代理人以及端到端代理人的示例。

**🧠 存储:**

存储指的是在链/代理人的调用之间保持状态的能力。LangChain为存储提供了一个标准接口，并提供了一系列存储实现以及使用存储的链/代理人的示例。

**🧐 评估:**

生成模型通常很难使用传统的度量标准进行评估。一种新的评估方法是使用语言模型自身来进行评估。LangChain提供了一些提示/链来辅助进行评估。

有关这些概念的更多信息，请参阅我们的[完整文档](https://python.langchain.com)。

## 💁 贡献

作为一个在快速发展的领域中的开源项目，我们非常欢迎贡献，不论是新功能、改进基础设施还是更好的文档。

有关如何贡献的详细信息，请参阅[这里](.github/CONTRIBUTING.md)。
