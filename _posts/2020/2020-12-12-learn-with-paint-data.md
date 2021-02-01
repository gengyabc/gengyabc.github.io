---
title: "使用绘制数据学习数据分析"
image: posts/20201212/PaintData-Example.png.webp
categories:
  - 数据分析
tags:
  - 分类
  - 聚类
---

[绘制数据]小部件可能看起来仅仅是一个玩具，但与其他小部件结合使用后，它可以直观地演示诸多机器学习概念（例如k均值，分层聚, SVM，逻辑回归，等等。）






## 介绍
该小部件使您可以在二维平面上绘制数据。您可以命名 x 和 y 轴，选择类别数（用不同的颜色表示），然后将点定位在图形上。

![](/assets/images/posts/20201212/PaintData-Example.png.webp)

多种绘画工具可让您根据自己的特定需求管理数据集: 使用`单个放置`绘制单个数据点或`毛刷`来绘制多个数据点。选择一个数据子集，然后在[数据表]小部件中查看它，或放大以查看您的点的位置。`抖动`和`磁吸`是功能相反的工具，可用于扩散实例或将它们拉近。

## 示例
### 在聚类中的应用
数据将在具有两个特征的数据表中表示，它们的实例对应于系统中的坐标。这样的数据集非常适合演示 `k均值` 和 `层级聚类` 方法。在下图中，我们看到具有特定设置的 `k均值` 和 `层次聚类` 识别聚类的比较。`k均值` 返回分数排名，其中最佳 **轮廓系数** 表示最可能的聚类数 (簇数), 但是最高的分数并不是我们期望的结果。在 `层次聚类` 中, 我们发现。

![](/assets/images/posts/20201212/PaintData-clusters.png.webp)

[<i class="fas fa-cloud-download-alt"></i>下载本工作流](/assets/workflows/2020/paintdata-clusters.ows)


### 在分类算法中的应用
使用 **绘制数据** 的另一种方法是观察分类算法的性能，在这里我们可以更改图形以演示预测模型的改进或退化。通过绘制数据点，我们可以尝试构建数据集，这对于一个分类器来说很困难，而对于另一个分类器来说很容易。比如，为什么 `线性SVM` 在以下数据集上失败？

![](/assets/images/posts/20201212/PaintData-TestLearners.png.webp)

[<i class="fas fa-cloud-download-alt"></i>下载本工作流](/assets/workflows/2020/paintdata-classifiers.ows)


{% include _links.md %}

