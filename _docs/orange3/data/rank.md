---
title: 排名(Rank)
---
对分类或回归分析中的特征重要性进行排名。




## 输入
- 数据: 输入数据集
- 评分器: 特征评分模型

## 输出
- 选中的数据: 被选择的数据集
- 评分: 含有特征评分的数据表
- 特征: 特征列表

## 功能
**排名(Rank)** 小部件会根据适用的评分方法，例如信息增益 information gain，卡方 chi-square 和线性回归 linear regression 以及支持评分的所有关联外部模型例如线性回归 linear regression，逻辑回归 logistic regression，另外，小部件也可以处理非监督数据，但只能由外部评分器(如主成分分析(PCA)处理。

## 界面

![](/assets/images/data/Rank-stamped.png.webp)

1. 选择评分方法。详见下文中[“评分方法”](#分类)部分中的分类、回归和非监督数据部分。
2. 手动选择要输出的属性。选择“无”将不会输出任何属性，若选择“所有”则会输出所有属性。“手动”会在右侧表中输出所选择的属性。“最佳排名”将通过当前排序方式输出n个最高排名属性。如果勾选了"自动发送"，则小部件会自动将更改传达给其他小部件。

## 评分方法
### 分类
1. 信息增益：期望的信息量（熵减）
2. [信息增益比]((https://en.wikipedia.org/wiki/Information_gain_ratio))：信息增益与属性固有信息的比值，可减少信息增益中多值特征的偏差
3. [基尼下降]((https://en.wikipedia.org/wiki/Gini_coefficient))：频率分布值之间的不等式，可以直观的反应差异。
4. [ANOVA](https://en.wikipedia.org/wiki/One-way_analysis_of_variance)：特征在不同类别中的平均值之间的差异，可找出对该事物有显著影响的因素。
5. X²(https://en.wikipedia.org/wiki/Chi-squared_distribution): 按卡方统计量度特征和类之间的依赖关系
6. [ReliefF](https://en.wikipedia.org/wiki/Relief_(feature_selection))：用属性区分相似数据实例上的类的能力
7. [FCBF (Fast Correlation Based Filter)](https://www.aaai.org/Papers/ICML/2003/ICML03-111.pdf)：基于熵的度量，还可以识别由于特征之间的成对相关性而引起的冗余

此外，也可以连接特定学习器，学习器可以根据特征在被构建的模型中的重要性（例如[逻辑回归]、[随机森林]、[随机梯度下降])对特征进行评分。注意，在排名之前，数据将会被标准化。

### 回归
1. 单变量回归：单个变量的线性回归
2. [RReliefF](http://www.clopinet.com/isabelle/Projects/reading/robnik97-icml.pdf): 两个实例的预测（类）值之间的相对距离。

此外，也可以连接回归学习器 (例如[线性回归]、[随机森林]、[随机梯度下降]). 同样的，在排名之前，数据将会被标准化。

### 非监督
目前，仅[主成分分析(PCA)][主成分分析]支持非监督数据。需要将主成分分析连接到“排名”以获取分数。分数与变量与各个主成分的相关性对应。

## 示例

### 属性排名与选择
下面，我们在[文件(File)][文件]小部件后使用了**排名(Rank)**小部件，以减少数据属性集并仅选出最有用的属性：

![](/assets/images/data/Rank-Select-Schema.png.webp)

下图展示了小部件输出仅包含得分最高的属性的数据集：

![](/assets/images/data/Rank-Select-Widgets.png.webp)

### 用于机器学习的特征子集选择
接下来是一个更复杂的示例。在下面的工作流程中，我们首先将数据分为训练集和测试集。在上半部分中，训练数据通过 **排名(Rank)** 小部件进行选择，以选择信息最丰富的属性，而在下半部分中，则没有进行特征选择。选择过特征的数据集和原始数据集都将传递到其自己的“测试和评分”小部件，这些数据将用于开发一个 **朴素贝叶斯分类器** 并在测试集上对其评分。

![](/assets/images/data/Rank-and-Test.png.webp)

对于具有许多特征的数据集，如上所示，朴素贝叶斯分类器进行特征选择通常会提高预测数据的准确性。

{% include _links.md %}
