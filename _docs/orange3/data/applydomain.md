---
title: 应用变换(Apply Domain)
---

给定数据集和模板，转换数据集。

## 输入
* 数据：输入数据集
* 模板数据：用于转换数据集的模板

## 输出
* 转换的数据：转换后的数据集

## 功能和界面
**应用变换(Apply Domain)** 将新数据映射到转换的空间中。例如，如果我们使用 **PCA** 转换某些数据并希望在同一空间中观察新数据，则可以使用**应用变换(Apply Domain)** 将新数据映射到由原始数据创建的 **PCA** 空间中。

![](/assets/images/data/ApplyDomain.png.webp)

此小部件输入为数据集和用于转换数据集的模板数据集。

## 示例
在此示例中，我们将使用[文件(File)][文件]小部件中的 *”iris“* 数据。 要创建两个单独的数据集，我们将使用[选择行(Select Rows)][选择行]并将条件设置为“ `iris is one of iris-setosa, iris-versicolor*`。 这将输出一个具有 100 行的数据集，其中一半属于*iris-setosa* ，另一半属于*iris-versicolor*。

我们将使用[PCA][PCA]转换数据，然后选择前两个分量，这些分量解释了 96％ 的变化。 现在，我们想对“新”数据进行相同的预处理，即剩下的 50 个 *iris virginicas*。 发送[选择行(Select Rows)][选择行]中未使用的数据到 **应用变换(Apply Domain)**。 确保使用“[选择行(Select Rows)][选择行]”小部件中的 `不匹配数据` 输出。然后添加从**PCA**输出的转换数据。

**应用变换(Apply Domain)** 将预处理器应用于新数据并输出。 要将新数据添加到旧数据，请使用[连接(Concatenate)][连接]。 将来自**PCA**的转换数据用作主要数据，并将来自应用域的转换数据用作附加数据。

在[数据表(Data Table)][数据表]或[散点图(Scatter Plot)][散点图]中观察结果，以查看与旧数据有关的新数据。

![](/assets/images/data/ApplyDomain-Example.png.webp)


{% include _links.md %}