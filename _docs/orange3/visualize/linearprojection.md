---
title: 线性投影(Linear Projection)
---

具有探索性数据分析的线性投影方法。






{% include_relative _point_inout.md %}
- 分量：投影向量

## 功能
该小部件显示已标记类别的数据的[线性投影](https://en.wikipedia.org/wiki/Projection_(linear_algebra)) 。 它支持各种类型的投影，例如圆形，[线性判别分析](https://en.wikipedia.org/wiki/Linear_discriminant_analysis)，[主要成分分析](https://en.wikipedia.org/wiki/Principal_component_analysis)，以及自定义投影。

考虑下面所示的 *Iris* 数据集的投影。 请注意，*sepal width* 和 *sepal length* 已经把 *Iris setosa* 与其他两个类别分开，而 *petal length* 是 *Iris versicolor* 与 *Iris virginica* 的最佳区分属性。

## 界面
![](/assets/images/visualize/linear-projection-stamped.png.webp)

1. 显示的投影轴和其他可用轴。
2. 通过使用 **“建议特征”** 优化投影。 此功能通过平均分类准确性为属性评分，并通过可视化同步更新返回得分最高的属性。
3. 选择投影类型。
4. 圆内的轴被隐藏。 圆半径可以使用滑块更改。

{% include_relative _point_view.md %}


## 示例
**线性投影(Linear Projection)** 小部件的工作方式与其他可视化小部件一样。 在下面，我们将其连接到[文件(File)][文件]小部件，以查看在二维平面上投影的集合。 然后，我们选择数据进行进一步分析，并将其连接到[数据表(Data Table)][数据表] 小部件，以查看所选子集的详细信息。

![](/assets/images/visualize/LinearProjection-example.png.webp)

## 参考文献

Koren Y., Carmel L. (2003). Visualization of labeled data using linear transformations. In Proceedings of IEEE Information Visualization 2003, (InfoVis'03). Available [here](http://citeseerx.ist.psu.edu/viewdoc/download;jsessionid=3DDF0DB68D8AB9949820A19B0344C1F3?doi=10.1.1.13.8657&rep=rep1&type=pdf).

Boulesteix A.-L., Strimmer K. (2006). Partial least squares: a versatile tool for the analysis of high-dimensional genomic data. Briefings in Bioinformatics, 8(1), 32-44. Abstract [here](http://bib.oxfordjournals.org/content/8/1/32.abstract).

{% include _links.md %}