---
title: 相关性（Correlations）
---

计算所有属性两两相关性。





## 输入
- 数据：输入数据集

## 输出
- 数据：输入数据集
- 特征：选定的一对特征
- 相关性：具有相关性得分的数据表

## 功能
**相(Correlations)** 为数据集中的所有特征对计算 `皮尔逊 Pearson` 或 `斯皮尔曼 Spearman` 相关系数。这些方法只能检测单调关系。

## 界面

![](/assets/images/data/Correlations-stamped.png.webp)

1. 相关性度量：
   * [皮尔逊](https://en.wikipedia.org/wiki/Pearson_correlation_coefficient) 相关性。
   * [斯皮尔曼](https://en.wikipedia.org/wiki/Spearman%27s_rank_correlation_coefficient) 相关性。
2. 筛选以查找属性对。
3. 具有相关系数的属性对的列表。按完成健以停止大型数据集的计算。
4. 访问小部件帮助并生成报告。

## 示例

只能为数字（连续）特征计算相关性，因此我们将使用 *housing* 作为示例数据集。将其加载到[文件(File)][文件]到**相关性(Correlations)** 小部件。正相关的特征对将在列表的顶部，负相关的特征对将在列表的底部。

![](/assets/images/data/Correlations-links.png.webp)

选择最负相关的特征对，`DIS-NOX`。现在，将[散点图(Scatter Plot)][散点图]部件连接到 **相关性(Correlations)** 小部件并设置两个输出。观察如何在散点图中设置特征对。在散点图中，看的出这两个特征确实属于负相关关系。

![](/assets/images/data/Correlations-Example.png.webp)

{% include _links.md %}