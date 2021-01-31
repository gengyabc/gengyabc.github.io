---
title: 维恩图(Venn Diagram)
---

为两个或更多数据子集绘制[维恩图](http://en.wikipedia.org/wiki/Venn_diagram)。





## 输入
- 数据：输入数据集

## 输出
- 选定数据：从图中选择的实例
- 数据：整个数据,添加了表示是否选择了一个实例的列

## 功能
**维恩图(Venn Diagram)** 小部件通过显示共同数据实例（行）或共享特征（列）的数量来显示数据集之间的逻辑关系。选择可视化的一部分将输出相应的实例或特征。

![](/assets/images/visualize/venn-workflow.png.webp)

## 界面
![](/assets/images/visualize/VennDiagram-stamped.png.webp)

1. 选择是对共同特征还是实例进行计数。
2. 选择是包含重复项还是仅输出唯一行（仅在按实例匹配时适用）。 如果 **自动发送** 处于启用状态，则更改将自动传给其他小部件。

行可以通过其标识进行匹配，例如 如果来自不同数据集的行来自文件中的同一行，则它们匹配。除了使用标识之外，我们还可以选择一个字符串变量来匹配行。如果数据集没有公共字符串变量，则会显示警告。

## 示例
使用 **维恩图(Venn Diagram)** 的最简单方法是选择数据子集并在可视化文件中找到匹配的实例。 我们使用 *breast-cancer* 数据集通过 [选择行(Select Rows)][选择行]小部件选择两个子集: 第一个子集是40至49岁的乳腺癌患者的子集，第二个是肿瘤大小在20到29之间的患者。 **维恩图(Venn Diagram)** 可以帮助我们找到与两个标准相对应的实例，可以在两个圆的交点处找到它们。

![](/assets/images/visualize/VennDiagram-Example1.png.webp)

**维恩图(Venn Diagram)** 小部件也可用于探索不同的预测模型。 在下面的示例中，我们分析了3种预测方法，即[朴素贝叶斯(Naive Bayes)][朴素贝叶斯]，[支持向量机(SVM)][支持向量机]和[随机森林(Random Forest)][随机森林]，根据它们的错误分类实例。

通过在三个[混淆矩阵(Confusion Matrix)][混淆矩阵]小部件中选择错误分类，然后将它们发送到**维恩图(Venn Diagram)**，我们可以看到每种使用方法可视化的所有错误分类实例。 然后，我们打开**维恩图(Venn Diagram)**，并选择例如通过所有三种方法识别的分类错误的实例。 这表示为所有三个圆的交点。 单击交叉点以查看在[散点图(Scatter Plot)][散点图]小部件中标记的这两个实例。尝试选择图的不同部分，以查看散点图的可视化方式如何变化。


![](/assets/images/visualize/VennDiagram-Example2.png.webp)

{% include _links.md %}