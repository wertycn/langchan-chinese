# 自定义示例选择器

在本教程中，我们将创建一个自定义示例选择器，该选择器从给定的示例列表中选择每个交替的示例。

一个 `ExampleSelector` 必须实现两个方法:

1. 一个 `add_example` 方法，接收一个示例并将其添加到 ExampleSelector 中
2. 一个 `select_examples` 方法，接收输入变量（用于用户输入）并返回用于 few shot prompt 的示例列表。

让我们实现一个自定义的`ExampleSelector`，它只是随机选择两个示例。

:::{note}
在LangChain中支持的当前示例选择器实现，请[点击这里](../../prompt_templates/getting_started.md)查看。
:::

<!-- TODO（shreya）：添加正确的链接。-->

## 实现自定义示例选择器

```python
from langchain.prompts.example_selector.base import BaseExampleSelector
from typing import Dict, List
import numpy as np


class CustomExampleSelector(BaseExampleSelector):
    
    def __init__(self, examples: List[Dict[str, str]]):
        self.examples = examples
    
    def add_example(self, example: Dict[str, str]) -> None:
        """Add new example to store for a key."""
        self.examples.append(example)

    def select_examples(self, input_variables: Dict[str, str]) -> List[dict]:
        """Select which examples to use based on the inputs."""
        return np.random.choice(self.examples, size=2, replace=False)

```


## 使用自定义示例选择器

```python

examples = [
    {"foo": "1"},
    {"foo": "2"},
    {"foo": "3"}
]

# Initialize example selector.
example_selector = CustomExampleSelector(examples)


# Select examples
example_selector.select_examples({"foo": "foo"})
# -> array([{'foo': '2'}, {'foo': '3'}], dtype=object)

# Add new example to the set of examples
example_selector.add_example({"foo": "4"})
example_selector.examples
# -> [{'foo': '1'}, {'foo': '2'}, {'foo': '3'}, {'foo': '4'}]

# Select examples
example_selector.select_examples({"foo": "foo"})
# -> array([{'foo': '1'}, {'foo': '4'}], dtype=object)
```
