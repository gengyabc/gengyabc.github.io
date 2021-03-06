---
title: 机器学习概述
---


机器学习是现代人工智能的核心，深度学习作为机器学习的一种方法，使得人工智能取得了突破性的进展。




## 机器学习分类
机器学习可以大致分为三种：监督学习，非监督学习和强化学习。
* 监督学习：从标记的训练数据来推断一个功能的机器学习任务。利用一组已知类别的样本调整分类器的参数，使其达到所要求性能的过程。
* 非监督学习：在未加标签的数据中，试图找到隐藏的结构。因为提供给学习者的实例是未标记的，因此没有错误信号来评估潜在的解决方案。
* 强化学习；智能体以“试错”的方式进行学习，通过与环境进行交互获得的奖赏指导行为，目标是使智能体获得最大的奖赏。

## 机器学习任务
下面我们以监督学习为例，看看一个机器学习任务到底是要做什么。

机器学习的任务可以简单理解为总结经验，发现规律，掌握规则，预测未来。

对于人类来说，我们可以通过历史经验，学习到一个规律。如果有新的问题出现，我们使用习得的历史经验，来预测未来未知的事情

![](/assets/images/ai/basic/02/human-learn.png.webp)

对于机器学习系统来说，它可以通过历史数据，学习到一个模型。如果有新的问题出现，它使用习得的模型，来预测未来新的输入

![](/assets/images/ai/basic/02/machine-learn.png.webp)

熟悉了机器学习的基本概念，我们应该发现，它的核心问题是模型怎么来的？更具体的问就是，模型的参数怎么优化的。

我们可以找一个模型的评分标准，然后最大化或者最小化这个分数。现在问题又转变为，这个评价标准是什么？怎么优化？这个评价标准就是[损失函数](/docs/ai/01basic/04loss/)。我们将这个损失函数的值不断降低，就是将模型的参数不断优化。



