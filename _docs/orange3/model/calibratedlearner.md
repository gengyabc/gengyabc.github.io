---
title: 校准器(Calibrated Learner)
---

用概率校准和决策阈值优化来包装另一个学习者。




{% include_relative _input.md%}
- 基学习器：要校准的学习器


## 输出
- 学习器：校准的学习算法
- 模型：使用经过校准的学习器训练的模型

## 功能
该学习器生成一个模型，该模型可校分类概率的分布并优化决策阈值。 该小部件仅适用于二元分类任务。

## 界面
![](/assets/images/model/Calibrated-Learner-stamped.png.webp)

1. 它将在其他小部件中显示的名称。 默认名称由学习器，校准和优化参数组成。
2. 概率校准：
    - [Sigmoid 校准](http://citeseer.ist.psu.edu/viewdoc/summary?doi=10.1.1.41.1639)
    - [Isotonic 校准](https://scikit-learn.org/stable/auto_examples/plot_isotonic_regression.html)
    - 不校准

3. 决策阈值优化：
    - 优化分类准确性
    - 优化 F1 score
    - 无阈值优化
{% include_relative _report_apply.md %}

## 示例
我们使用 *titanic* 数据集，因为小部件需要二元类值（在这种情况下，它们是“生存”和“未生存”的）。

我们将使用[逻辑回归(Logistic Regression)][逻辑回归]作为基学习器，我们将使用默认设置进行校准，即通过分布值的 sigmoid 优化和通过优化准确率进行校准。

将结果与未经校准的 [逻辑回归(Logistic Regression)][逻辑回归] 模型进行比较，我们可以看到校准后的模型表现更好。

![](/assets/images/model/Calibrated-Learner-Example.png.webp)

## 参考文献
1. [Why Calibrators? Part 1 of the Series on Probability Calibration](https://towardsdatascience.com/why-calibrators-part-1-of-the-series-on-probability-calibration-9110831c6bde)
2. [Calibration](https://towardsdatascience.com/tagged/calibration)
3. [1.16. Probability calibration](https://scikit-learn.org/stable/modules/calibration.html)


{% include _links.md %}