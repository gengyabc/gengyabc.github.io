---
title: 流形学习(Manifold Learning)
---

非线性降维。





## 输入
- 数据：输入数据集

## 输出
- 转换的数据：维度减少的数据集

## 功能
[流形学习](https://en.wikipedia.org/wiki/Nonlinear_dimensionality_reduction)是一种在高维空间内找到非线性流形的技术。小部件将输出与二维空间相对应的新坐标。其后可以使用[散点图(Scatter Plot)][散点图]或其他可视化窗口小部件来可视化此类数据。


## 界面
![](/assets/images/unsupervised/manifold-learning-stamped.png.webp)

1. 流形学习方法:
   - [t-SNE](http://scikit-learn.org/stable/modules/manifold.html#t-distributed-stochastic-neighbor-embedding-t-sne)
   - [MDS](http://scikit-learn.org/stable/modules/manifold.html#multi-dimensional-scaling-mds), see also [MDS][多维尺度分析]
   - [Isomap](http://scikit-learn.org/stable/modules/manifold.html#isomap)
   - [Locally Linear Embedding](http://scikit-learn.org/stable/modules/manifold.html#locally-linear-embedding)
   - [Spectral Embedding](http://scikit-learn.org/stable/modules/manifold.html#spectral-embedding)
2. 设置参数:
   - t-SNE (distance measures):
     - *Euclidean* distance
     - *Manhattan*
     - *Chebyshev*
     - *Jaccard*
     - *Mahalanobis*
     - *Cosine*
   - MDS (iterations and initialization):
     - *max iterations*: maximum number of optimization interactions
     - *initialization*: method for initialization of the algorithm (PCA or random)
   - Isomap:
     - number of *neighbors*
   - Locally Linear Embedding:
     - *method*:
       - standard
       - modified
       - [hessian eigenmap](http://scikit-learn.org/stable/modules/manifold.html#hessian-eigenmapping)
       - local
     - number of *neighbors*
     - *max iterations*
   - Spectral Embedding:
     - *affinity*:
       - nearest neighbors
       - RFB kernel
3. 输出：精简特征（成分）的数量。
4. 如果勾选了 **自动应用**，则更改将自动传播。 或者，单击**应用**。
5. 生成报告。

**流形学习(Manifold Learning)** 小部件为高维数据生成不同的嵌入


![](/assets/images/unsupervised/collage-manifold.png.webp)

从左到右，从上到下：t-SNE, MDS, Isomap, Locally Linear Embedding 和 Spectral Embedding.

## 示例
**流形学习(Manifold Learning)** 小部件可将高维数据转换为低维近似值。这非常适合可视化具有许多特征的数据集。 我们使用 *voting.tab* 将 16 维数据映射到 2D 图形上。然后，我们使用[散点图(Scatter Plot)][散点图]绘制嵌入图。

![](/assets/images/unsupervised/manifold-learning-example.png.webp)

{% include _links.md %}