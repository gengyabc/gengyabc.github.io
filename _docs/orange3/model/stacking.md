---
title: 堆叠(Stacking)
---

堆叠多个模型。





{% include_relative _input.md%}


- 学习器：学习算法
- 组合方法：模型组合方法

## 输出
- 学习器：组合的学习算法
- 模型：训练过的模

## 功能
**堆叠(Stacking)** 是一种集成方法，可以从多个基本模型计算出元模型。 **堆叠(Stacking)** 小部件具有 **组合方法** 输入，它提供了一种用于组合输入模型的方法。如果未提供 **组合方法** 输入，则使用默认方法:用于分类的 “逻辑回归” 和用于回归问题的 “岭回归”。

## 界面
![](/assets/images/model/Stacking-stamped.png.webp)

1. 可以给学习器一个名称，该名称将出现在其他小部件中。 默认名称是“堆叠(Stacking)”
{% include_relative _report_apply.md %}


## 示例
我们将使用[绘制数据(Paint Data)][绘制数据]演示如何使用小部件。我们绘制了一个带有4个类别标签的复杂数据集，并将其发送到[测试与评分(Test & Score)][测试与评分]。 我们还提供了三个[k 近邻(kNN)][k 近邻]学习器，每个学习器具有不同的参数（邻居数为 5、10 或 15）。 评估结果不错，但是我们可以做得更好吗？

让我们使用 **堆叠(Stacking)** 。**堆叠(Stacking)** 要求输入的多个学习器和一种组合方法。在我们的例子中，这是[逻辑回归(Logistic Regression)][逻辑回归]。 然后，将构建的元学习器发送到 [测试与评分(Test & Score)][测试与评分]。 即使只是微不足道的结果也有所改善。 **堆叠(Stacking)** 通常可以在复杂的数据集上很好地工作。


![](/assets/images/model/Stacking-Example.png.webp)

{% include _links.md %}
