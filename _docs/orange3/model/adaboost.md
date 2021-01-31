---
title: 自适应提升算法(AdaBoost)
---
一个集合了若干弱学习器并适应每个训练样本“难度”的集成元算法。


{% include_relative _input.md%}
- 学习器：学习算法

## 输出
- 学习器：adaboost 学习算法
- 模型：训练过的模型

## 功能
[AdaBoost](https://en.wikipedia.org/wiki/AdaBoost),自适应增强(Adaptive boosting)的缩写, 是一种机器学习算法，由[Yoav Freund and Robert Schapire](https://cseweb.ucsd.edu/~yfreund/papers/IntroToBoosting.pdf)提出。它可以与其他学习算法一起使用以提高其性能。这通过调整弱学习器来实现。
**自适应提升算法(AdaBoost)** 适用于分类和回归。

## 界面
![](/assets/images/model/AdaBoost-stamped.png.webp)

1. 可以给学习器一个名称，该名称将出现在其他小部件中。 默认名称是“自适应提升算法(AdaBoost)”。
2. 设置参数。 基学习器树，您可以设置：
     - `基学习器数目`
     - `学习率`：它确定新获取的信息将在多大程度上覆盖旧信息（0表示学习器将不学习任何信息，1表示学习器仅考虑最新信息）
     - `随机发生器的固定种子`：设置一个固定种子，以重现结果。
3. 提升方法。
    - `分类算法`（如果是分类问题）：SAMME（使用分类结果更新基本估计量的权重）或SAMME.R（使用概率估计更新基本估计量的权重）。
    - `回归损失函数`（如果是回归问题）：线性，平方，指数。
{% include_relative _report_apply.md %}

## 示例
为了进行分类，我们加载了 *iris* 数据集。 我们使用**自适应提升算法(AdaBoost)** ，[树(Tree)][树]和[逻辑回归(Logistic Regression)][逻辑回归]，并在[测试与评分(Test & Score)][测试与评分]查看与比较结果。


![](/assets/images/model/AdaBoost-classification.png.webp)

为了进行回归，我们加载了 *housing* 数据集，将数据实例发送到两个不同的模型: **自适应提升算法(AdaBoost)** ，[树(Tree)][树]，并将它们输出到[预测(Predictions)][预测]小部件。


![](/assets/images/model/AdaBoost-regression.png.webp)

{% include _links.md %}