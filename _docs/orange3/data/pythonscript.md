---
title: Python脚本(Python Script)
---

通过 Python 脚本来扩展功能。





## 输入
- 数据(Orange.data.Table)：输入数据集绑定到 `in_data` 变量
- 学习器(Orange.classification.Learner): 输入学习器绑定到 `in_learner` 变量
- 分类器(Orange.classification.Learner): 输入分类器绑定到 `in_classifier` 变量
- 对象: 输入 Python 对象绑定到 `in_object` 变量

## 输出
- 数据(Orange.data.Table): 从 `out_data` 变量获取的数据集
- 学习器 (Orange.classification.Learner): 从 `out_learner` 变量获取的学习器
- 分类器 (Orange.classification.Learner): 从 `out_classifier` 变量获取的分类器
- 对象: 从 `out_object` 变量获取到的对象

## 功能
当现有小部件中的功能不能很好的实现需求时，**Python脚本(Python Script)** 小部件可用于在输入中运行 python 脚本。 脚本具有 `in_data`, `in_distance`, `in_learner`, `in_classifier` 与 `in_object` 变量(来自输入) 在其本地命名空间中.如果输入未连接或未收到任何数据, 这些变量将会 `None`.

脚本执行后，会从脚本的本地命名空间里提取变量，并用作小部件的输出。**Python脚本(Python Script)** 小部件可以进一步连接到其他小部件，以观察输出。

如下示例，这个脚本只会简单地传递其接收到的所有信号:

```python
out_data = in_data
out_distance = in_distance
out_learner = in_learner
out_classifier = in_classifier
out_object = in_object
```

注意：我们不应 "in place" 方式修改输入对象。

## 界面

![](/assets/images/data/PythonScript-stamped.png)

1. "信息"框包含橙现智能 **Python脚本(Python Script)** 的基本运算变量的名称。
2. "库"可用于管理多个脚本。按 "+" 将添加新条目并在 **Python脚本(Python Script)** 编辑器中打开它。修改脚本时，它在库中的条目将更改，以指示其具有未保存的更改。单击“更新”按钮将保存脚本（键盘快捷键"Ctrl+S"）。可以通过选择脚本并按下 "-" 按钮来删除该脚本。
3. 在"运行"框中按"执行"将执行脚本（键盘快捷方式"Ctrl+R"）。 任何脚本输出（从 `print` ）将被捕获并显示在脚本下方的控制台中。
4. **Python脚本(Python Script)** 编辑器可用于编辑脚本（它支持一些基本的语法的高亮显示）。
5. 控制台显示脚本的输出。

## 示例
**Python脚本(Python Script)** 小部件旨在为高级用户拓展功能。[文档](https://docs.biolab.si/3/data-mining-library/#reference)中介绍了 Orange 库中的类。若要查找有关 Orange 表类的详细信息，请参阅[Table](https://docs.biolab.si/3/data-mining-library/reference/data.table.html), [Domain](https://docs.biolab.si/3/data-mining-library/reference/data.domain.html), 和 [Variable](https://docs.biolab.si/3/data-mining-library/reference/data.variable.html)文档。

### 第一个例子
例如，可以按属性进行批处理筛选。示例使用 “zoo.tab”，并筛选出具有多于 5 个离散值的所有属性。在我们的案例中，这仅删除了 “leg” 属性，但请想象一个示例，其中会有许多这样的属性。

```python
from Orange.data import Domain, Table
domain = Domain([attr for attr in in_data.domain.attributes
                 if attr.is_continuous or len(attr.values) <= 5],
                in_data.domain.class_vars)
out_data = Table(domain, in_data)
```

![](/assets/images/data/PythonScript-filtering.png)


### 第二个例子

展示了如何在几行代码中舍入所有值。这次我们用了 `housing.tab` 并将所有值四舍五入为整数。
```python
import numpy as np
out_data = in_data.copy()
#copy, otherwise input data will be overwritten
np.round(out_data.X, 0, out_data.X)
```

![](/assets/images/data/PythonScript-round.png)

### 第三个例子

在数据中引入了一些高斯噪声。我们再次复制输入数据，然后用两个for循环遍历所有值并添加随机噪声。

```python
import random
from Orange.data import Domain, Table
new_data = in_data.copy()
for inst in new_data:
  for f in inst.domain.attributes:
    inst[f] += random.gauss(0, 0.02)
out_data = new_data
```
![](/assets/images/data/PythonScript-gauss.png)

### 最后一个示例

使用 `Orange3-Text` 插件。 **Python脚本(Python Script)** 对于文本挖掘中的自定义预处理，从字符串中提取新特征或利用 `nltk` 或 `gensim` 功能非常有用。 在下面，我们通过按空格将"deerwester.tab" 中的输入数据简单地分词。

```python
print('Running Preprocessing ...')
tokens = [doc.split(' ') for doc in in_data.documents]
print('Tokens:', tokens)
out_object = in_data
out_object.store_tokens(tokens)
```

您可以添加许多其他预处理步骤来进一步调整输出。**Python脚本(Python Script)** 的输出可与任何接受脚本生成的输出类型的小部件一起使用。 在这种情况下，连接线为绿色，表示 "词云" 小部件的输入类型正确。

![](/assets/images/data/PythonScript-Example3.png)