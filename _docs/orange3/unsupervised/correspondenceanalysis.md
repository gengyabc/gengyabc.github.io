---
title: 对应分析(Correspondence Analysis)
---

分类多元数据的对应分析。





## 输入
- 数据：输入数据集

## 输出
- 坐标：所有成分的坐标

## 功能
[对应分析](https://en.wikipedia.org/wiki/Correspondence_analysis)（CA）计算输入数据的 CA 线性变换。虽然与 PCA 相似，但 CA 会根据离散数据而不是连续数据计算线性变换。



## 界面

![](/assets/images/unsupervised/CorrespondenceAnalysis-stamped.png.webp)

1. 选择要查看的变量。
2. 选择每个坐标轴的成分。
3. [惯性](https://en.wikipedia.org/wiki/Sylvester%27s_law_of_inertia)值（独立于变换的百分比，即变量在同一维中）。
4. 生成报告。

## 示例

以下是 **对应分析(Correspondence Analysis)** 和[散点图(Scatter Plot)][散点图] 在  *Titanic* 数据集上的简单比较。 尽管 [散点图(Scatter Plot)][散点图] 可以很好地显示出哪个类别和性别的生存率很高，但是 **对应分析(Correspondence Analysis)** 可以绘制数个变量的二维图，因此很容易看到变量值之间的关系。从图中可以清楚地看出 *no*，*male* 和 *crew* 彼此相关。 *yes*, *female* 和 *first* 也是如此。


![](/assets/images/unsupervised/CorrespondenceAnalysis-Example.png.webp)

{% include _links.md %}