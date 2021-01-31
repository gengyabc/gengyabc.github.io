---
title: 常量预测(Constant)
---

从训练集中预测最频繁的类别或平均值。






{% include_relative _input.md%}

## 输出
* 学习器：多数/平均学习算法
* 模型：已训练的模型

## 功能
该学习器生成的模型始终预测一个常数值, 分类任务中是[多数(majority)](https://en.wikipedia.org/wiki/Predictive_modelling#Majority_classifier) ,  回归任务中是[均值](https://en.wikipedia.org/wiki/Mean)

分类时，当使用[预测(Predictions)][预测] 预测类别值时，小部件将返回训练集中类别的相对频率。当存在两个或更多多数类时，分类器会随机选择预测类，但对于特定示例始终返回相同的类。

对于回归，它学习目标变量的平均值，并返回具有相同平均值的预测器。

该小部件通常用作其他模型的基准。

## 界面
![](/assets/images/model/Constant-stamped.png.webp)

该小部件为用户提供了两个选项：

1. 它将在其他小部件中显示的名称。 默认名称为“常量预测(Constant)”。
2. 生成报告。

如果更改窗口小部件的名称，则需要单击**应用**。 或者，勾选左侧的框以自动传达。


## 示例
在一个典型的分类示例中，我们将使用此小部件与其他学习算法（例如kNN）的分数进行比较。使用 *iris* 数据集并将其连接到 [测试与评分(Test & Score)][测试与评分]。 然后将 **常量预测(Constant)** 和 [k 近邻(kNN)][k 近邻] 连接到[测试与评分(Test & Score)][测试与评分]，并观察[k 近邻(kNN)][k 近邻] 相比这个常数的预测值如何。


![](/assets/images/model/Constant-classification.png.webp)

对于回归，我们使用 **常量预测(Constant)** 在[预测(Predictions)][预测] 中构造一个预测变量。 我们使用了 *housing* 数据集。 在[预测(Predictions)][预测] 中，您可以看到 **平均值学习器** 为所有实例返回一个（平均值）值。


![](/assets/images/model/Constant-regression.png.webp)

{% include _links.md %}