---
title: CN2 规则归纳(CN2 Rule Induction)
---

使用 CN2 算法从数据中归纳出规则。





{% include_relative _input.md%}


## 输出
- 学习器：CN2学习算法
- CN2规则分类器：训练有素的模型

## 功能
CN2算法是一种分类技术，设计用于即使在可能存在噪声的域中，也可以有效地归纳简单的，易于理解的规则，形式为 “如果...则预测...”。

**CN2规则归纳** 仅适用于分类

## 界面
![](/assets/images/model/CN2-stamped.png.webp)

1. 学习器出现在其他小部件中的名称。 默认名称是 **CN2 规则归纳器**。
2. `规则排序`：
    - `有序`：归纳有序规则（决策列表）。找到规则条件，并在规则头中分配多数类。
    - `无序`：归纳无序规则（规则集）。分别学习关于原始学习数据每个类别的规则。
3. `覆盖算法`：
    - `互斥`：覆盖学习实例后，下一步不再考虑中。
    - `加权`：覆盖学习实例后，减小其权重（乘以 *gamma*），进而减小其对算法进一步迭代的影响。
5. `规则搜索`：
    - `评估指标`：选择一种启发式方法来评估发现的假设：
      - [熵](https://en.wikipedia.org/wiki/Entropy_(information_theory)) （不可预测性的度量）
      - [拉普拉斯精度](https://en.wikipedia.org/wiki/Laplace%27s_method)
      - 加权相对精度
    - `集束宽度`: 记住迄今为止找到的最佳规则，并监视固定数量的替代方案（光束）。
6. `规则筛选`：
    - `最小规则覆盖范围`：找到的规则必须至少覆盖所覆盖示例的最小所需数量。无序规则必须涵盖许多目标类示例。
    - `最大规则长度`：找到的规则最多可以组合选择器（条件）的最大允许数量。
    - `默认alpha`：重要性测试，用于修剪有关类的初始分布的最专门（不太常用）的规则。
    - `父Alpha`：进行重要性测试，以针对父类分布修剪出最专门的（较不经常使用的）规则。

{% include_relative _report_apply.md %}



## 示例

我们使用了 *zoo* 数据集，并将其传递给 **CN2规则归纳**。 我们可以使用[CN2 规则查看器(CN2 Rule Viewer)][CN2 规则查看器] 小部件查看和解释构建的模型。

![](/assets/images/model/CN2-visualize.png.webp)

第二个工作流程测试评估[测试与评分(Test & Score)][测试与评分]中的 **CN2规则归纳** 和[树(Tree)][树]。


![](/assets/images/model/CN2-classification.png.webp)

## 参考文献

1. Fürnkranz, Johannes. "Separate-and-Conquer Rule Learning", Artificial Intelligence Review 13, 3-54, 1999.
2. Clark, Peter and Tim Niblett. "The CN2 Induction Algorithm", Machine Learning Journal, 3 (4), 261-283, 1989.
3. Clark, Peter and Robin Boswell. "Rule Induction with CN2: Some Recent Improvements", Machine Learning - Proceedings of the 5th European Conference (EWSL-91),151-163, 1991.
4. Lavrač, Nada et al. "Subgroup Discovery with CN2-SD",Journal of Machine Learning Research 5, 153-188, 2004

{% include _links.md %}