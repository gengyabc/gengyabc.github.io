---
title: 自组织映射(Self-Organizing Map)
---

自组织映射的计算。






## 输入

- 数据：输入数据集

## 输出
- 选定数据：从图中选择的实例
- 数据：带有附加列的数据，显示是否选择了一个点

## 功能
[自组织映射（SOM）](https://en.wikipedia.org/wiki/Self-organizing_map)是一种人工神经网络（ANN），它使用无监督学习进行训练，以产生数据的二维的离散表示。这是一种降维的方法。自组织映射使用邻域函数保留输入空间的拓扑属性。

网格中的点表示数据实例。默认情况下，点的大小与该点表示的实例数相对应。这些点按多数类别（如果可用）进行着色，而内部颜色的强度表示多数类别的比例。要查看类别分布，请选择 **“显示饼图”** 选项。

与其他可视化小部件一样，**自组织映射（SOM）** 也支持交互式选择组。 使用 `Shift` 键选择一个新组，然后使用 `Ctr + Shift` 键添加到现有组。

## 界面
![](/assets/images/unsupervised/Self-Organizing_Map-stamped.png.webp)

1. SOM属性：
    - 设置网格类型。 选项为六角形或正方形网格。
    - 如果选中 **“自动设置尺寸”**，则图的大小将自动设置。 或者，手动设置尺寸。
    - 设置 SOM 投影的初始化类型。选项包括 `PCA 初始化`，`随机初始化`和`可复制的随机`（random_seed = 0）。
    - 设置完参数后，按 **开始** 重新运行优化。
2. 设置图中实例的颜色。小部件默认情况下按类别着色（如果可用）。
    - **显示饼图** 将点变成饼图，显示用于着色的值的分布。
    - **按实例数量设置大小** 根据该点表示的实例数量缩放这些点。


## 示例
**自组织映射(Self-Organizing Map)** 是输入数据的低维投影。我们将使用 *brown-selected* 数据，并以二维投影形式显示数据实例。好像这三种基因类型是分开的。我们可以从网格中选择一个子集，并将其显示在数据表中。


![](/assets/images/unsupervised/Self-Organizing_Map_Example.png.webp)
