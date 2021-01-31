---
title: 散点图(Scatter Plot)
---

具有探索性分析和智能数据可视化增强功能的散点图可视化.





## 输入
- 数据：输入数据集
- 数据子集：实例的子集
- 特征：属性列表

## 输出

- 选定数据：从图中选择的实例
- 数据：带有附加列的数据，显示是否选择了一个点

## 功能
**散点图(Scatter Plot)** 小部件提供了连续属性的二维散点图可视化。数据显示为点的集合。可以在小部件的左侧调整图形的各种属性，例如颜色，点的大小和形状，轴标题，最大点大小和抖动。下面的截图显示了*Iris* 数据集的散点图以及分类属性的颜色匹配。


## 界面
![](/assets/images/visualize/Scatterplot-Iris-stamped.png.webp)

1. 选择 x 轴 和 y 轴。 通过使用 `查找信息投影` 优化您的投影。此功能通过平均分类准确性对属性对进行评分，并通过可视化同步更新返回得分最高的特征对。 设置[抖动](https://en.wikipedia.org/wiki/Jitter)以防止点重叠。 
2. 设置显示点的颜色（离散值将变彩色，连续点将变灰度点）。设置 `标签`，`形状`和`大小`以区分点。 设置所有数据点的符号大小和不透明度。 设置所需的颜色比例。
   
3. 调整图属性：
    - **显示图例** 在右侧显示图例。 单击并拖动图例将其移动。
    - **显示网格线** 显示绘图后的网格。
    - **在鼠标悬停时显示所有数据** 如果将光标放在点上，则会启用信息提示框。
    - **显示颜色区域** 按分类为图表着色（请参见下面的屏幕截图）。
    - **显示回归线** 绘制一对连续属性的回归线。
4. **选择，缩放，平移和缩放以适合** 是浏览图形的选项 
5. 如果勾选了 **“自动发送”**，则会自动更改。 或者，按 **发送**。
6. **保存图像** 将创建的图像以 *.svg* 或 *.png* 格式保存到您的计算机。
7. 生成报告。

如下是一个示例

![](/assets/images/visualize/Scatterplot-ClassDensity.png.webp)

## 高级功能
### 智能数据可视化

如果数据集具有许多属性，则不可能手动查看所有特征对，以找到有趣或有用的散点图。 橙现智能通过小部件中的 **查找信息投影** 选项实现了智能数据可视化。

如果在 **“颜色”** 部分中选择了分类变量，则[评分](http://eprints.fri.uni-lj.si/210/) 的计算如下: 对于每个数据实例，该方法在投影的2D空间中（即在属性对的组合上）找到10个最近的邻居。然后检查其中有多少具有相同的颜色。投影的总分就是同色邻居的平均数。

连续颜色的计算类似，不同之处在于[决定系数](https://en.wikipedia.org/wiki/Coefficient_of_determination) 用于测量投影的局部均匀性。

要使用此方法，请转到小部件中的 **查找信息投影** 选项，打开子窗口，然后按 **开始**。 该功能将按平均分类准确率得分返回属性对列表。

下面是一个演示排名的示例。为简化起见，我们使用 *Iris* 数据集。 运行 **查找信息投影** 优化后，找到了的更好投影

![](/assets/images/visualize/ScatterPlotExample-Ranking.png.webp)

### 选择
选择可用于手动定义数据中的子组。选择数据实例以将其放入新组时，请使用 `Shift` 修饰符。 `Shift + Ctrl`（在 `mac`上为 `Shift + Cmd`）会将实例附加到最后一个组。

信号数据输出带有附加列的数据表，该列包含组索引。


![](/assets/images/visualize/ScatterPlot-selection.png.webp)

### 探索性数据分析

与橙现智能控件的其余小部件一样，**散点图(Scatter Plot)** 支持放大和缩小图以及手动选择数据实例。 这些功能在小部件的左下角可用。

默认工具是 `选择`，用于选择所选矩形区域内的数据实例。 `抓取` 使您可以在窗格周围移动散点图。 使用`缩放`，您可以使用鼠标滚动来放大和缩小窗格，而`重置缩放`可以将可视化重置为最佳大小。 下面显示了一个简单的示例，其中我们从一个矩形区域中选择了数据实例，并将其发送到[数据表(Data Table)][数据表]小部件。 请注意，散点图并未显示全部52个数据实例，因为某些数据实例重叠了（它们使用的两个属性都具有相同的值）。


![](/assets/images/visualize/ScatterPlotExample-Explorative.png.webp)

## 示例

**散点图(Scatter Plot)** 可以与任何输出选定数据的小部件组合。 在下面的示例中，我们将[树(Tree)][树]和 **散点图(Scatter Plot)** 结合起来，以显示从选定决策树节点获取的实例（单击树上的任何节点将发送一组 选定的数据实例到散点图中，并用填充符号标记选定的实例）。

![](/assets/images/visualize/ScatterPlotExample-Classification.png.webp)

## 参考文献

Gregor Leban and Blaz Zupan and Gaj Vidmar and Ivan Bratko (2006) VizRank: Data Visualization Guided by Machine Learning. Data Mining and Knowledge Discovery, 13 (2). pp. 119-136. Available [here](http://eprints.fri.uni-lj.si/210/).

{% include _links.md %}