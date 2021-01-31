---
title: 距离矩阵(Distance Matrix)
---

可视化距离矩阵中的距离度量。





## 输入
- 距离：距离矩阵

## 输出
- 距离：距离矩阵
- 表格：距离矩阵中的距离度量

## 功能
**距离矩阵(Distance Matrix)** 小部件创建一个距离矩阵，该矩阵是一个二维数组，其中包含一组元素之间成对的距离。数据集中的元素数量决定了矩阵的大小。数据矩阵对于层次聚类至关重要，在生物信息学中也非常有用，它们用于以坐标独立的方式表示蛋白质结构。

<!-- TODO: 不完整 -->
## 界面
![](/assets/images/unsupervised/DistanceMatrix-stamped.png.webp)

1. 数据集中的元素及其之间的距离。
2. 标记表格。 选项包括：*无*，*枚举*，*根据变量*。
3. 生成报告。
4. 单击*发送*以将更改传达给其他窗口小部件。 或者，勾选*发送*按钮前面的框，更改将自动传达（*自动发送*）。

**距离矩阵(Distance Matrix)** 仅有的两个合适输入是[距离(Distances)][距离] 和 [距离变换(Distance Transformation)][距离变换]小部件。小部件的输出是一个包含距离矩阵的数据表。用户可以决定如何标记表格，然后可以在单独的数据表中可视化或显示距离矩阵（或距离矩阵中的实例）。


## 示例
以下示例显示了 **距离矩阵(Distance Matrix)** 小部件的非常标准用法。 我们从 *Iris* 数据集中计算出样本中各行之间的距离，并将其输出到 **距离矩阵(Distance Matrix)** 中。 *Iris Virginica* 和 *Iris Setosa* 相距最远就不足为奇了。

![](/assets/images/unsupervised/DistanceMatrix-Example.png.webp)

{% include _links.md %}

