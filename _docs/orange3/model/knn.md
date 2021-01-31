---
title: k 近邻(kNN)
---
根据最靠近的训练实例进行预测。

{% include_relative _input.md%}

## 输出
- 学习器：kNN 学习算法
- 模型：训练有素的模型

## 功能
**k 近邻(kNN)** 小部件使用[kNN算法](https://en.wikipedia.org/wiki/K-nearest_neighbors_algorithm)在特征空间中搜索k个最近的训练示例并将其平均值用作预测。

## 界面
![](/assets/images/model/kNN-stamped.png.webp)

1. 一个名称，该名称将出现在其他小部件中。 默认名称是“k近邻(kNN)”。
2. 设置最近邻居的数量，距离参数（度量）和权重作为模型标准。
     - 度量可以是：
         - [欧几里得](https://en.wikipedia.org/wiki/Euclidean_distance)（“直线”，两点之间的距离）
         - [曼哈顿](https://en.wikipedia.org/wiki/Taxicab_geometry)（所有属性的绝对差之和）
         - [最大值](https://en.wikipedia.org/wiki/Chebyshev_distance)（属性之间的绝对最大差异）
         - [Mahalanobis](https://en.wikipedia.org/wiki/Mahalanobis_distance)（点与分布之间的距离）。
     - 可以使用的 **权重** 是：
         - `统一`：每个邻域中的所有点均被同等加权。
         - `距离`：查询点附近的邻居比远处的邻居影响更大。

{% include_relative _report_apply.md %}

## 示例

第一个示例是对 *iris* 数据集的分类任务。 我们将**k 近邻(kNN)** 的结果与默认模型[常量预测(Constant)][常量预测]进行比较，该模型始终会预测多数分类。


![](/assets/images/model/Constant-classification.png.webp)

第二个示例是回归任务。 此工作流程显示了如何使用 **k 近邻(kNN)** 输出。 出于本示例的目的，我们使用了 *housing* 数据集。 我们将 **k 近邻(kNN)** 预测模型输入到[预测(Predictions)][预测]中，并观察预测值。

![](/assets/images/model/kNN-regression.png.webp)

{% include _links.md %}