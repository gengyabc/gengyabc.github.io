---
title: 轮廓图(Silhouette Plot)
---

数据集群内一致性的图形表示。





## 输入
- 数据：输入数据集

## 输出
- 选定数据：从图中选择的实例
- 数据：整个数据,添加了表示是否选择了一个实例的列

## 功能
**轮廓图(Silhouette Plot)** 小部件提供了数据聚类内一致性的图形表示，并为用户提供了直观评估聚类质量的方法。**轮廓分数** 是衡量对象与其自身的聚类相比于其他聚类的相似程度的度量，并且在创建轮廓图时至关重要。轮廓得分接近 1 表示数据实例接近聚类的中心，而轮廓得分接近 0 的实例位于两个聚类之间的边界上。

## 界面
![](/assets/images/visualize/SilhouettePlot-stamped.png.webp)
1. 选择距离度量。 您可以选择：
    -[欧几里得](https://en.wikipedia.org/wiki/Euclidean_distance) （两点之间的“直线”距离）
    -[曼哈顿](https://en.wiktionary.org/wiki/Manhattan_distance) （所有属性的绝对差之和）
    -[余弦](https://en.wiktionary.org/wiki/Cosine_similarity) （1-两个向量之间的夹角余弦）
2. 选择聚类标签。 您可以决定是否按聚类对实例进行分组。
3. 显示选项：
{% include_relative _save_and_report.md %}
7. 创建的轮廓图。


## 示例

我们决定对 *iris* 数据集使用**轮廓图(Silhouette Plot)**。 我们选择了轮廓分数较低的数据实例，并将其作为子集传递给[散点图(Scatter Plot)][散点图]小部件。由于您可以清楚地看到子集位于两个聚类之间的边界中，因此此可视化仅确认 **轮廓图(Silhouette Plot)** 小部件的准确性。

![](/assets/images/visualize/SilhouettePlot-Example.png.webp)

了解更多, [请参考](http://blog.biolab.si/2016/03/23/all-i-see-is-silhouette/).

{% include _links.md %}