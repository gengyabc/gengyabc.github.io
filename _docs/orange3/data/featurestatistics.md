---
title: 特征统计(Feature Statistics)
---

显示特征的基本统计数据

## 输入
- 数据：输入数据集

## 输出
- 选中的数据：仅包含所选特征表
- 统计：该表包含所选特征的统计信息    

## 功能
**特征统计(Feature Statistics)** 小部件提供了一种快速检查和查找给定数据集中特征的方法。

## 界面
![](/assets/images/data/feature_statistics-stamped.png.webp)

**特征统计(Feature Statistics)** 小部件应用于 *heart-disease* 数据集。出于说明目的，`exerc ind ang` 已手动更改为元变量。

1. 有关当前数据集大小，数量和特征类型的信息
2. 右侧的直方图可以通过任何特征进行着色。如果所选特征是分类特征，则使用离散的调色板（如示例中所示）。 如果所选特征是数字特征，则使用连续调色板。右侧的表格包含有关数据集中每个特征的统计信息。可以按我们现在描述的每个统计信息对特征进行排序。
3. 特征类型-可以是分类，数字，时间和字符串之一。
4. 特征名称。

5. 特征值的直方图。 如果特征是数字，则我们适当地将值离散化为 bin。 如果特征是分类的，则在直方图中为每个值分配自己的条形图。
6. 特征值的集中趋势。对于分类特征，这是[模](https://en.wikipedia.org/wiki/Mode_(statistics))。对于数字特征，这是[平均值](https://en.wikipedia.org/wiki/Mean)。
7. 特征值的离散度。对于分类特征，这是值分布的[熵](https://en.wikipedia.org/wiki/Entropy_(information_theory))。 对于数字特征，这是[变异系数](https://en.wikipedia.org/wiki/Coefficient_of_variation)。
8. 最小值。这是针对数字和有序分类特征计算的。
9. 最大值。是针对数字和有序分类特征计算的。
10. 数据中缺失值的数量。

还要注意，某些行的颜色不同。白色行表示常规特征，灰色行表示类别变量，而较浅的灰色表示元变量。

## 示例

**特征统计(Feature Statistics)** 小部件最常在[文件(File)][文件]小部件之后使用，以检查和查找给定数据集中潜在感兴趣特征。 在以下示例中，我们使用 *heart-disease* 数据集。


![](/assets/images/data/feature_statistics_workflow.png.webp)

一旦找到了潜在感兴趣特征的子集，或者发现了我们想排除的特征，我们只需选择要保留的特征即可。该小部件仅输出具有这些特征的新数据集。

![](/assets/images/data/feature_statistics_example1.png.webp)

另外，如果我们要存储特征统计信息，则可以使用 `统计` 输出并根据需要操纵这些值。 在此示例中，我们仅选择所有特征并将统计信息显示在表格中。

![](/assets/images/data/feature_statistics_example2.png.webp)

{% include _links.md %}
