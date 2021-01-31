---
title: 线性回归(Linear Regression)
---

具有可选L1（LASSO），L2（岭）或L1L2（弹性网）正则化的线性回归算法。





{% include_relative _input.md%}

## 输出

- 学习器：线性回归学习算法
- 模型：训练过的模型
- 系数: 线性回归系数


## 功能
**线性回归(Linear Regression)** 小部件构造了一个学习器/预测器，该学习器/预测器从其输入数据中学习[线性函数](https://en.wikipedia.org/wiki/Linear_regression)。该模型可以识别预测变量 *x* 和响应变量 *y* 之间的关系。另外，可以指定[Lasso](https://en.wikipedia.org/wiki/Least_squares#Lasso_method)和[Ridge](https://en.wikipedia.org/wiki/Least_squares#Lasso_method)正则化参数。 

线性回归仅适用于回归任务。

## 界面
![](/assets/images/model/LinearRegression-stamped.png.webp)

1. 学习器/预测器的名字
2. 选择要训练的模型：
    - 无正规化
    - [岭](https://en.wikipedia.org/wiki/Least_squares#Lasso_method)正则化（L2）
    - [套索](https://en.wikipedia.org/wiki/Least_squares#Lasso_method)正则化（L1）
    - [弹性网](https://en.wikipedia.org/wiki/Elastic_net_regularization)正则化

{% include_relative _report_apply.md %}

## 示例
下面是 *housing* 数据集的简单工作流程。 我们训练了**线性回归(Linear Regression)** 和[随机森林(Random Forest)][随机森林]，并在[测试与评分(Test & Score)][测试与评分]中评估了它们的效果。


![](/assets/images/model/LinearRegression-regression.png.webp)


{% include _links.md %}