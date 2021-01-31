---
title: 树(Tree)
---

具有正向剪枝的树算法。





{% include_relative _input.md%}

## 输出

- 学习器：决策树学习算法
- 模型：训练过的模型

## 功能
**树(Tree)** 是一种简单的算法，可通过类别纯度将数据拆分为节点。 它是[随机森林(Random Forest)][随机森林]的前身。**树(Tree)**  可以处理离散数据集和连续数据集,可以用于分类和回归任务。

## 界面
![](/assets/images/model/Tree-stamped.png.webp)

1. 可以给学习器一个名称，该名称将出现在其他小部件中。 默认名称是“树(Tree)”。
2. 树参数：
    - `归纳二叉树`：构建一棵二叉树（分为两个子节点）
    - `叶中最小实例数`：如果选中，拆分不会将少于指定数量的训练示例放入分支中。
    - `不要拆分小于以下值的子集`：禁止算法分割少于给定实例数的节点。
    - `将树最大深度限制为`：将分类树的深度限制为指定数量的节点级别。
3. `当多数达到[％]时停止`：在达到指定的多数阈值后停止拆分节点

{% include_relative _report_apply.md %}

## 示例
此小部件有两种典型用法。一个是您可能要引入一个模型并在[查看树(Tree Viewer)][查看树]中检查它。


![](/assets/images/model/Tree-classification-visualize.png.webp)

第二个是训练模型并比对[逻辑回归(Logistic Regression)][逻辑回归]评估其性能。

![](/assets/images/model/Tree-classification-model.png.webp)

我们在两个示例中都使用了 *iris* 数据集。 但是，**树(Tree)** 也适用于回归任务。 使用 *housing* 数据集并将其传递给 **树(Tree)**。 从[查看树(Tree Viewer)][查看树]中选择的树节点显示在[散点图(Scatter Plot)][散点图]中，我们可以看到所选示例具有相同的特征。


![](/assets/images/model/Tree-regression-subset.png.webp)


{% include _links.md %}