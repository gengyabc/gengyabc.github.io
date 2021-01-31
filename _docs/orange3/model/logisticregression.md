---
title: 逻辑回归(Logistic Regression)
---

具有LASSO（L1）或脊（L2）正则化的逻辑回归分类算法。






{% include_relative _input.md%}

## 输出

- 学习器：逻辑回归学习算法
- 模型：训练过的模型
- 系数: 逻辑回归系数

## 功能
**逻辑回归(Logistic Regression)** 从数据中学习[逻辑回归](https://en.wikipedia.org/wiki/Logistic_regression)模型。 它仅适用于分类任务。


## 界面
![](/assets/images/model/LogisticRegression-stamped.png.webp)

1. 学习器在其他小部件中使用的名称。 默认名称是“逻辑回归(Logistic Regression)”。
2. [正则化类型](https://en.wikipedia.org/wiki/Regularization_(mathematics))类型:[L1](https://en.wikipedia.org/wiki/Least_squares#Lasso_method)或[L2](https://en.wikipedia.org/wiki/Tikhonov_regularization)。 设置正则化强度（默认为C = 1）。
   
{% include_relative _report_apply.md %}


## 示例
在 *hayes-roth_learn* 数据集上通过 **逻辑回归(Logistic Regression)** 演示预测结果。我们首先在[文件(File)][文件]小部件中加载 *hayes-roth_learn* ，然后将数据传递给 **逻辑回归(Logistic Regression)** 。 然后，我们将训练后的模型传递给[预测(Predictions)][预测]。

现在，我们要预测新数据集上的类别。 我们在第二个[文件(File)][文件]小部件中加载 *hayes-roth_test* ，并将其连接到[预测(Predictions)][预测]。 现在，我们可以直接在[预测(Predictions)][预测]中观察使用 **逻辑回归(Logistic Regression)** 预测的类别。


![](/assets/images/model/LogisticRegression-classification.png.webp)

{% include _links.md %}