---
title: 近邻(Neighbors)
---

根据参考计算数据中最近的邻居。




## 输入
- 数据：输入数据集
- 参考数据：计算近邻的参考数据

## 输出
- 邻居：根据参考数据计算的最近邻居的数据表

## 功能
<!-- TODO: 翻译有缺陷 -->
**近邻(Neighbors)** 小部件会计算给定参考数据和给定距离度量值的最近邻居。参考数据可以是一个实例，也可以是多个实例。在一个参考数据的情况下，小部件计算最接近的 `n` 个实例，其中 `n` 由小部件中的“邻居数”选项设置。当参考数据包含更多实例时，小部件将计算每个数据实例的组合距离，作为到每个参考的最小距离。小部件以最小的组合距离输出 `n` 个数据实例。

## 界面
![](/assets/images/data/neighbours-stamped.png.webp)

1. 用于计算邻居的距离度量。 支持的度量是：欧几里得，曼哈顿，马哈拉诺比斯，余弦，雅卡德，斯皮尔曼，绝对斯皮尔曼，皮尔逊，绝对皮尔逊 (Euclidean, Manhattan, Mahalanobis, Cosine, Jaccard, Spearman, absolute Spearman, Pearson, absolute Pearson)。
2. 输出中的邻居数。
3. ~~如果选中*排除行（等于引用），则与引用高度相似（距离<1e-5）的数据实例将被排除~~
4. 单击 "应用" 提交更改。 要自动发送更改，请勾选 ”自动应用“。
5. 状态栏，可查看小部件帮助以及有关输入和输出数据的信息。

## 示例
### 第一个示例
我们使用 "iris" 数据并将其传递给 **近邻(Neighbors)** 和[数据表(Data Table)][数据表]。 在[数据表(Data Table)][数据表]中，我们选择了一个鸢尾花(iris)实例，它将作为我们的参考数据，这意味着我们希望检索 10 个最接近所选数据的实例。 我们也将[数据表(Data Table)][数据表]连接到 **近邻(Neighbors)**。

我们可以在 **数据表(Data Table)** 中观察近邻计算的结果，在其中可以看到10个最接近所选鸢尾花的实例。

![](/assets/images/data/neighbours-example1.png.webp)

现在，选择 **数据表(Data Table)** 更改为多个示例。结果，我们得到的实例与参考数据的组合距离最近。 该方法将组合距离计算为到每个参考的最小距离

![](/assets/images/data/neighbours-example-multiple.png.webp)

<!-- TODO: Another example requires the installation of Image Analytics add-on. We loaded 15 paintings from famous painters with **Import Images** widget and passed them to **Image Embedding**, where we selected *Painters* embedder.

Then the procedure is the same as above. We passed embedded images to **Image Viewer** and selected a painting from Monet to serve as our reference image. We passed the image to **Neighbors**, where we set the distance measure to *cosine*, ticked off *Exclude reference* and set the neighbors to 2. This allows us to find the actual closest neighbor to a reference painting and observe them side by side in **Image Viewer (1)**.

![](/assets/images/data/neighbours-example2.png.webp) -->

{% include _links.md %}

