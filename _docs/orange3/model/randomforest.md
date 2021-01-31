---
title: 随机森林(Random Forest)
---

使用一组决策树进行预测。





{% include_relative _input.md%}

## 输出

- 学习器：随机森林学习算法
- 模型：训练过的模型


## 功能
[随机森林](https://en.wikipedia.org/wiki/Random_forest)是一种用于分类，回归和其他任务的集成学习方法。 它最初是由[何天琴](https://en.wikipedia.org/wiki/Tin_Kam_Ho)提出的，然后由莱奥·布雷曼（Leo Breiman，Breiman，2001）和阿黛尔·卡特勒（Adele Cutler）进一步开发。

**随机森林** 建立一组决策树。 每棵树都是从训练数据的引导样本中得到的。在生长单个树时，将长出特征的任意子集（因此使用术语“随机”），从中选择用于拆分的最佳特征。最终模型基于森林中独立生长的树木的多数投票。

**随机森林** 适用于分类和回归任务。

## 界面
![](/assets/images/model/RandomForest.png.webp)

1. 指定模型名称。 默认名称是“随机森林(Random Forest)”。
2. 基本特性：
    - `树木数量`：指定森林中将包含多少棵决策树。
    - `每个拆分考虑的属性数目`：指定每个节点多少个随机属性。 如果未勾选，则此数字等于数据中属性数的平方根。
    - `可重复训练`：固定随机种子，从而实现结果的可重复性。
    - `平衡类别分布`：[将类别权重设置为出现频率的反比]((https://scikit-learn.org/stable/modules/generation/sklearn.utils.class_weight.compute_class_weight.html?highlight=sklearn%20utils%20class_weight))。
5. 生长控制：
    - `单个树的深度`：Breiman 最初的建议是在不进行任何预修剪的情况下生长树，但是由于预修剪通常效果很好且速度更快，因此用户可以设置树的生长深度。
    - `小于...不要拆分`：选择可以拆分的最小子集。
  
{% include_relative _report_apply.md %}

## 示例
对于分类任务，我们使用 *iris* 数据集。 将其连接到[预测(Predictions)][预测]。 然后，将[文件(File)][文件]连接到 **随机森林(Random Forest)** 和[树(Tree)][树]并将它们进一步连接到[预测(Predictions)][预测]。 最后，观察两个模型的预测。


![](/assets/images/model/RandomForest-classification.png.webp)

对于回归任务，我们将使用 *housing* 数据。 在这里，我们将在[测试与评分(Test & Score)][测试与评分]中比较不同的模型，即 **随机森林(Random Forest)** ，[线性回归(Linear Regression)][线性回归]和[常量预测(Constant)][常量预测]。 


![](/assets/images/model/RandomForest-regression.png.webp)

## 参考文献

Breiman, L. (2001). Random Forests. In Machine Learning, 45(1), 5-32. Available [here](https://www.stat.berkeley.edu/~breiman/randomforest2001.pdf).


{% include _links.md %}