---
title: 箱线图(Box Plot)
---
显示属性值的分布。






## 输入
- 数据: 输入数据集

## 输出
- 选定数据：从图中选择的实例
- 数据：带有附加列的数据，显示是否选择了一个点


## 功能
**箱线图(Box Plot)** 小部件显示属性值的分布。使用此小部件检查任何新数据以快速发现异常是一种最佳实践，例如重复的值（例如，橙色和橘色），离群值等

## 界面
![](/assets/images/visualize/BoxPlot-Continuous-stamped.png.webp)

1. 选择要绘制的变量。 选中 `按相关性排序`，以对所选子组按 `Chi2` 或 `ANOVA` 排序变量。
2. 选择 `子组` 以查看由离散子组显示的[箱形图](https://en.wikipedia.org/wiki/Box_plot) 。
3. 将实例按子组分组时，可以更改显示模式。带注释的框将显示最终值，均值和中位数，而比较中位数和比较均值会在子组之间比较所选值。

![continuous](/assets/images/visualize/BoxPlot-Continuous-small.png.webp)

4.平均值（深蓝色垂直线）。细蓝线代表[标准差](http://mathworld.wolfram.com/StandardDeviation.html)。
5.第一个（25％）和第三个（75％）分位数的值。 蓝色高亮显示的区域表示第一个和第三个四分位数之间的值。
6.中位数（黄色垂直线）。
7.如果勾选了 **“自动发送”**，则会自动传达更改。 或者，按 **发送**。
8.访问帮助，保存图像或生成报告。

对于离散属性，条形图代表具有每个特定属性值的实例数。 该图显示了 *Zoo* 数据集中不同动物类型的数量：共有41种哺乳动物，13种鱼类，20种鸟类，依此类推。

![](/assets/images/visualize/BoxPlot-Discrete.png.webp)

## 示例

**箱线图(Box Plot)** 小部件最常在[文件(File)][文件]小部件之后使用，以观察数据集的统计属性。 在第一个示例中，我们使用 *heart-disease* 数据来检查变量。

![](/assets/images/visualize/BoxPlot-Example1.png.webp)

**箱线图(Box Plot)** 对于查找特定数据集的属性也很有用，例如，在另一个小部件中手动定义的一组实例, 例如[散点图(Scatter Plot)][散点图], 聚类或树节点。现在让我们使用 *zoo* 数据并使用[距离(Distances)][距离] 和 [层次聚类(Hierarchical Clustering)][层次聚类]创建一个典型的聚类工作流。 

现在定义聚类选择的阈值（单击顶部的标尺）。将 **箱线图(Box Plot)** 连接到[层次聚类(Hierarchical Clustering)][层次聚类]，勾选 `按相关性排序`，然后选择 `Cluster` 作为子组。 这将根据属性定义所选子组（在我们的情况下是聚类）的程度来对属性进行排序。 似乎我们的聚类确实与动物类型非常吻合！

![](/assets/images/visualize/BoxPlot-Example2.png.webp)

{% include _links.md %}