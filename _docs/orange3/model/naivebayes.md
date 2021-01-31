---
title: 朴素贝叶斯(Naive Bayes)
---

基于贝叶斯定理的假设特征独立的快速简单概率分类器。





{% include_relative _input.md%}

## 输出
- 学习器：朴素贝叶斯学习算法
- 模型：训练过的模型

## 功能
**朴素贝叶斯(Naive Bayes)** 从数据中学习[朴素贝叶斯](https://en.wikipedia.org/wiki/Naive_Bayes_classifier)模型。 它仅适用于分类任务。


## 界面
![](/assets/images/model/NaiveBayes-stamped.png.webp)

1. 学习器在其他小部件中使用的名称。 默认名称是“朴素贝叶斯(Naive Bayes)”。
{% include_relative _report_apply.md %}

## 示例
在这里，我们介绍了此小部件的两种用法。 首先，我们比较
**朴素贝叶斯(Naive Bayes)** 与[随机森林(Random Forest)][随机森林]。 我们将 *iris* 数据从[文件(File)][文件]连接到[测试与评分(Test & Score)][测试与评分]。 我们还将 **朴素贝叶斯(Naive Bayes)** 和[随机森林(Random Forest)][随机森林]连接到[测试与评分(Test & Score)][测试与评分]，并观察其预测分数。


![](/assets/images/model/NaiveBayes-classification.png.webp)

第二个方案显示了使用 **朴素贝叶斯(Naive Bayes)** 进行的预测的质量。 我们将**朴素贝叶斯(Naive Bayes)** 提供给[测试与评分(Test & Score)][测试与评分]小部件，然后将数据发送到[混淆矩阵(Confusion Matrix)][混淆矩阵]。 我们还将[散点图(Scatter Plot)][散点图]与[文件(File)](../../data/file/)连接在一起。 然后，我们在[混淆矩阵(Confusion Matrix)][混淆矩阵]中选择分类错误的实例，然后将其显示给[散点图(Scatter Plot)][散点图]。 散点图中的粗体点是来自 **朴素贝叶斯(Naive Bayes)** 的错误分类的实例。


![](/assets/images/model/NaiveBayes-visualize.png.webp)

{% include _links.md %}