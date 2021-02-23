---
title: 线性回归
---

介绍回归的基本概念，进而引出最小二乘法，最后看看如何判断拟合的好坏。







## 回归

统计学中，回归是确定两种或两种以上变量间相互依赖的定量关系的一种统计分析方法。
机器学习中，回归是一种预测性的建模技术，它研究的是特征和标记之间的关系。

回归可以简单分为线性回归和逻辑回归两种。

下面我们以简单线性回归为例，看看回归是什么。

### 简单线性回归

简单线性回归处理的问题就是：$y = wx + b$ 的问题。在机器学习中，$y$ 是标记，$x$ 是特征，$w$是权重，$b$是偏置。简单线性回归就是通过已知的 $x$ 和 $y$ 求解未知的 $w$ 和 $b$。

以年薪与工龄的关系为例，来看看简单线性回归的公式的意义。

偏置就是直线与纵轴的交点，权重其实就是斜率。简单线性回归就是找到合适的权重和偏置，使这条线尽可能的接近这些点的分布。

![](/assets/images/ai/models/01/reg.png)

### 多元线性回归

和简单线性回归类似，多元线性回归的问题是：$y = b + w_1x_2 + w_2x_2 + ... + w_n x_n$，他要通过已知的 $x_i$ 和 $y$ 求解未知的 $w_i$ 和 $b$


## 亲自动手

转到[亲自动手](/docs/tutorial/02linear_regression/)


## 最小二乘法

我们已经知道了回归是要让回归线能够尽可能的接近这些点的分布，下一步问题就来了，怎么保证尽可能接近点的分布呢？我们可以用最小二乘法来解答这个问题。

![](/assets/images/ai/models/01/ols.png)

假设观测到的实际数据点纵坐标 $y_i$，从这个点作垂线，与拟合的直线交点的纵坐标记为 $\hat{y_i}$。拟合的好的话，我们可以理解为想要每一组 $y_i$ 和 $\hat{y_i}$ 尽可能的接近。但是如果采用 $y_i - \hat{y_i}$ 的话，各个观测值与拟合值差的和 $\Sigma{(y_i - \hat{y_i})}$ 会正负值互相抵消，并不能真正反映我们需要的接近程度。所以，我们采用 $(y_i - \hat{y_i})^2$ 来度量每个观测点和拟合值接近程度，它们的和 $\Sigma{(y_i - \hat{y_i})^2}$ 的大小来判断接近程度的好坏。可以看出，这个值越小，拟合程度越好，最小二乘法要做的，就是最小化 $\Sigma{(y_i - \hat{y_i})^2}$。 

> $\dfrac {1}{m} \Sigma{(y_i - \hat{y_i})^2}$ 就是均方差 -- Mean Squared Error(MSE)，这里 $m$ 是样本数目。


## 判断拟合好坏

很多时候，机器学习工程师将 $\Sigma{(y_i - \hat{y_i})^2}$ 最小化之后就结束工作了。但是对于统计学家来说，还要继续判断模型的解释能力，即度量响应的变化中可由自变量解释的部分所占的比例。

{% include ai/_r2.md %}


