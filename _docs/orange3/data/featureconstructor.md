---
title: 特征构造器(Feature Constructor)
---

为数据集构造新特征





## 输入
- 数据：输入数据集

## 输出
- 数据：添加特征之后的数据集

## 功能
**特征构造器(Feature Constructor)** 允许您手动将特征（列）添加到数据集中。新特征可以是对现有一个或多个特征的组合进行计算（加，减等）。您可以选择特征的类型（离散，连续或字符串）以及其参数（名称，值，表达式）。对于连续变量，您只需要用 `Python` 构造一个表达式。

## 界面
![](/assets/images/data/feature-constructor1-stamped.png.webp)

1. 构造的变量列表
2. 添加或删除变量
3. 新特征名称
4. `Python` 表达式
5. 选择一个特征
6. 选择一个函数
7. 制作报告
8. 按 “发送” 发送更改

### 离散变量
但是，对于离散变量，还有更多工作要做。
* 首先添加或删除新特征所需的值。 
* 然后选择基值和表达式。 

在下面的示例中，我们构造了一个表达式 `if lower than`，并定义了三个条件： 如果原始值小于6，则为0（我们将其重命名为`low`），如果原始值小于7，则为1（`mid`），其他所有值都为2（`higher`）。请注意，我们为特征名称使用下划线（例如 `petal_length`）。

![](/assets/images/data/feature-constructor2-stamped.png.webp)

1. 变量定义列表
2. 添加或删除变量
3. 新特征名称
4. `Python` 表达式
5. 选择一个特征
6. 选择一个函数
7. 赋值
7. 制作报告
8. 按 “发送” 发送更改

## 示例
使用**特征构造器(Feature Constructor)**，您可以轻松地将现有特征调整或组合为新特征。
下面，我们向 “Titanic” 数据集添加了一个新的离散特征。我们创建了一个名为 `Financial status` 的新特征，如果此人属于头等舱（`status = first`），则将其值设置为 `rich`；对于其他所有人，则将值设置为 `not rich`。 我们可以通过[数据表(Data Table)][数据表]小部件看到新的数据集
.

![](/assets/images/data/FeatureConstructor-Example.png.webp)

## 提示

如果您不熟悉 `Python` 数学的表达式，这个一个快速入门。

- `+`, `-`： 加，减
- `*` ：乘
- `/`： 除
- `% `：取余数
- `**`： 乘方
- `//`： 求商（取整除）
- `<`, `>`, `<=`, `>= `：小于，大于，小于或等于，大于或等于
- `==`： 相等
- `!=`： 不等

更多[参考](http://www.tutorialspoint.com/python/python_basic_operators.htm).

{% include _links.md %}
