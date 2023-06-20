# 笔记本

本笔记本介绍如何将.ipynb笔记本中的数据加载到适合LangChain使用的格式中。

<!-- 警告：此文件是自动生成的！请勿编辑！而是编辑具有位置和名称的笔记本。 -->


```python
from langchain.document_loaders import NotebookLoader
```


```python
loader = NotebookLoader("example_data/notebook.ipynb")
```

`NotebookLoader.load()` 方法将`.ipynb`笔记本文件加载到一个`Document`对象中。

**参数**：

* `include_outputs`（bool）：是否在结果文档中包含单元格输出（默认为False）。
* `max_output_length`（int）：每个单元格输出中要包含的最大字符数（默认为10）。
* `remove_newline`（bool）：是否从单元格源代码和输出中删除换行符（默认为False）。
* `traceback` (bool): 是否包含完整的回溯信息（默认为False）。


```python
loader.load(include_outputs=True, max_output_length=20, remove_newline=True)
```
