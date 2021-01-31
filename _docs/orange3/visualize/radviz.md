---
title: Radviz
---

Radviz 可视化，具有探索性数据分析和智能数据可视化增强功能。





{% include_relative _point_inout.md %}
- 成分：Radviz向量

## 功能
Radviz（Hoffman et al。1997）是一种非线性的多维可视化技术，可以显示二维投影中由三个或更多变量定义的数据。可视化变量表示为围绕单位圆周长等距分布的锚点。数据实例显示为圆内的点，其位置由物理隐喻确定：每个点都用弹簧固定在适当的位置，弹簧的另一端连接到可变锚点上。每个弹簧的刚度与相应变量的值成比例，并且该点最终在弹簧力处于平衡的位置。 在可视化之前，将变量值缩放为介于 0 和 1 之间。与一组变量锚点接近的数据实例对于这些变量的值要比其他变量更高。

下面显示的快照显示了 **Radviz** 小部件，具有可视化的功能基因组学数据集（Brown等，2000）。 在此特定的可视化中，数据实例根据相应的类别进行着色，而可视化空间根据计算出的类别概率进行着色。 请注意，特定的可视化很好地分隔了不同类的数据实例，使可视化变得有趣并且可能提供信息。


## 界面
![](/assets/images/visualize/Radviz-Brown.png.webp)

1. 显示的投影轴和其他可用轴。
2. 通过使用 **“建议特征”** 优化投影。 此功能通过平均分类准确性为属性评分，并通过可视化同步更新返回得分最高的属性。
3. 选择投影类型。
4. 圆内的轴被隐藏。 圆半径可以使用滑块更改

{% include_relative _point_view.md %}


![](/assets/images/visualize/Radviz-Brown-2.png.webp)

## 参考文献

Hoffman, P. E. et al. (1997) DNA visual and analytic data mining. In the Proceedings of the IEEE Visualization. Phoenix, AZ, pp. 437-441.

Brown, M. P., W. N. Grundy et al. (2000). "Knowledge-based analysis of microarray gene expression data by using support vector machines." Proc Natl Acad Sci U S A 97(1): 262-7.

Leban, G., B. Zupan et al. (2006). "VizRank: Data Visualization Guided by Machine Learning." Data Mining and Knowledge Discovery 13(2): 119-136.

Mramor, M., G. Leban, J. Demsar, and B. Zupan. Visualization-based cancer microarray data classification analysis. Bioinformatics 23(16): 2147-2154, 2007.

{% include _links.md %}