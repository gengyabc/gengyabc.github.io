---
title: 距离图(Distance Map)
---
可视化项目之间的距离。





## 输入
- 距离：距离矩阵

## 输出
- 数据：从矩阵中选择的实例
- 特征：从矩阵中选择属性

## 功能
**距离图(Distance Map)** 可视化对象之间的距离。 可视化效果与我们打印出数字表的方式相同，只是数字被彩色斑点代替。

距离通常是实例之间的距离（[距离(Distances)][距离]小部件中的 “行”）或属性（[距离(Distances)][距离] “列”）之间的距离。 **距离图(Distance Map)** 的唯一合适输入是[距离(Distances)][距离] 小部件。 对于输出，用户可以选择图的区域，小部件将输出相应的实例或属性。另请注意，[距离(Distances)][距离] 小部件会忽略离散值，仅计算连续数据的距离，因此，如果需要先用[连续化(Continuize)][连续化]才可以显示离散数据的距离图。


下图显示了 *heart disease* 数据中各列之间的距离，其中较小的距离用浅色表示，较大的颜色用深橙色表示。矩阵是对称的，对角线是淡橙色的阴影, 属性与其自身没有区别。始终假定对称性，而对角线也可以为非零。


## 界面
![](/assets/images/unsupervised/DistanceMap-stamped.png.webp)

1. `元素排序`通过以下方式排列图中的元素
    - `无`: 按数据集中找到的实例顺序列出
    - `聚类`: 按相似性聚合
    - `有序叶聚类`: 最大程度增加相邻元素的相似度之和
2. `颜色`
    - `颜色`:为您的距离图选择调色板
    - `低`和`高`是调色板的阈值（实例或距离较小的属性为低，实例或距离较大的属性为高）。
3. 选择`注释`。
4. 如果 **自动发送** 已打开，则数据子集会自动进行通信，否则您需要按 **发送所选**。
5. 如果要将创建的图像保存到计算机，请按 **保存图像**。
6. 生成报告。

通常，调色板用于可视化出现在矩阵中的整个距离范围。可以通过设置低和高阈值来更改。这样，我们将忽略此间隔之外的距离差异，并可视化分布的有趣部分。

下面，我们通过将高距离的颜色阈值设置为最小来可视化 *heart disease*数据集中最相关的属性（按列的距离）。我们得到的主要是黑色正方形，其中距离得分最低的属性由所选颜色模式的较浅阴影表示（在我们的示例中为橙色）。在对角线旁边，我们看到在示例中 *ST by exercise* 和 *major vessels colored* 是两个最接近的属性。


![](/assets/images/unsupervised/DistanceMap-Highlighted.png.webp)

用户可以通过单击并拖动光标来选择图中的区域。 选地图的一部分时，小部件将输出所选单元格中的所有项目。


## 示例
第一个工作流程显示了 **距离图(Distance Map)** 小部件的非常标准的用法。 我们选择原始 *Iris* 数据的 70％ 作为样本，并在 **距离图(Distance Map)** 中查看行之间的距离。


![](/assets/images/unsupervised/DistanceMap-Example1.png.webp)

在第二个示例中，我们再次使用 *heart disease* 数据并仅从[散点图(Scatter Plot)][散点图]中选择了一部分女性。然后，我们在 **距离图(Distance Map)** 中可视化列之间的距离。由于子集还包含一些离散数据，因此[距离(Distances)][距离]小部件会警告我们它将忽略离散特征，因此在图中将仅看到连续的实例/属性。

![](/assets/images/unsupervised/DistanceMap-Example.png.webp)

{% include _links.md %}

