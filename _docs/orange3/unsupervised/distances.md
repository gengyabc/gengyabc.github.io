---
title: 距离(Distances)
---

计算数据集中行/列之间的距离。






## 输入
- 数据：输入数据集

## 输出
- 距离：距离矩阵

## 功能

**距离(Distances)** 小部件可计算数据集中行或列之间的距离。默认情况下，将对数据进行归一化以确保平等对待各个特征。 归一化总是按列进行。

稀疏数据使用 *Euclidean*，*Manhattan* 和 *Cosine* 度量

可以将生成的距离矩阵进一步发送到[层次聚类(Hierarchical Clustering)][层次聚类]以发现数据中的组，再发送到[距离图(Distance Map)][距离图]或[距离矩阵(Distance Matrix)][距离矩阵]以可视化距离（ 对于较大的数据集，距离矩阵可能会非常慢），发送到[MDS][多维尺度分析]以使用距离矩阵映射数据实例，最后将其保存为[保存距离矩阵(Save Distance Matrix)][保存距离矩阵]。 可以使用[距离文件(Distance File)][距离文件]加载距离文件。


## 界面
![](/assets/images/unsupervised/Distances-stamped.png.webp)

1. 选择是测量行还是列之间的距离。
2. 选择 **距离度量**

   - [Euclidean](https://en.wikipedia.org/wiki/Euclidean_distance): 两点之间的直线距离 
   - [Manhattan](https://en.wiktionary.org/wiki/Manhattan_distance): 所有属性的绝对差之和
   - [Cosine](https://en.wikipedia.org/wiki/Cosine_similarity): 内积空间的两个向量之间的夹角的余弦
   - [Jaccard](https://en.wikipedia.org/wiki/Jaccard_index): 交集的大小除以样本集并集的大小
   - [Spearman](https://en.wikipedia.org/wiki/Spearman's_rank_correlation_coefficient): 值的秩之间的线性相关性，重新映射为[0，1]之间的距离
   - [Spearman absolute](https://en.wikipedia.org/wiki/Spearman's_rank_correlation_coefficient): 值的秩的绝对值之间的线性相关性，重新映射为[0，1]之间的距离
   - [Pearson](https://en.wikipedia.org/wiki/Pearson_product-moment_correlation_coefficient) 值之间的线性相关性，重新映射为[0，1]之间的距离
   - [Pearson absolute](https://en.wikipedia.org/wiki/Pearson_product-moment_correlation_coefficient) 值的绝对值之间的线性相关性，重新映射为[0，1]之间的距离
   - [Hamming](https://en.wikipedia.org/wiki/Hamming_distance): 相应值不同的特征数量
   - [Bhattacharyya distance](https://en.wikipedia.org/wiki/Bhattacharyya_distance): 两个概率分布之间的相似度，不是真实距离，因为它不服从三角形不等式。
    归一化特征。 归一化总是按列进行。值以零为中心并缩放。
    在有缺失值的情况下，小部件会自动填充行或列的平均值。
    该小部件可用于数字数据和分类数据。 对于分类数据，如果两个值相同（“绿色”和“绿色”），则距离为0；如果两个值不同（“绿色”和“蓝色”），则距离为1。
3. 勾选 **自动应用** 以自动将更改提交到其他窗口小部件。 或者，按 **应用**。


## 示例

第一个示例显示了**距离(Distances)** 小部件的典型用法。 我们使用[文件(File)][文件]小部件中的 *iris.tab* 数据。 我们计算数据实例（行）之间的距离，并将结果传递给[层次聚类(Hierarchical Clustering)][层次聚类]。 这是查找数据实例组的简单工作流程。


![](/assets/images/unsupervised/Distances-Example1-rows.png.webp)

另外，我们可以计算列之间的距离，并发现我们的特征有多相似。


![](/assets/images/unsupervised/Distances-Example1-columns.png.webp)

第二个示例显示如何可视化所得距离矩阵。观察数据相似性的一种好方法是在[距离图(Distance Map)][距离图]或[MDS][多维尺度分析]中。


![](/assets/images/unsupervised/Distances-Example2.png.webp)

{% include _links.md %}
