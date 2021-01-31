---
title: 毕达哥拉斯森林(Pythagorean Forest)
---

毕达哥拉斯森林，用于可视化随机森林。





## 输入
- 随机森林：随机森林中的多个树模型

## 输出
- 树：选定的树模型

## 功能
**毕达哥拉斯森林(Pythagorean Forest)** 显示了从[随机森林(Random Forest)][随机森林]小部件中学习到的所有决策树模型。它将它们显示为各个毕达哥拉斯树，每个可视化都与一棵随机构造的树有关。在可视化中，您可以选择一棵树并将其显示在[毕达哥拉斯树(Pythagorean Tree)][毕达哥拉斯树]小部件中。最好的树是树枝最短，颜色最深的树。这意味着几乎没有属性可以很好地拆分分支。

小部件显示分类和回归结果。分类需要数据集中的离散目标变量，而回归则需要连续目标变量。它们都应在输入中输入[树(Tree)][树]。


## 界面
![](/assets/images/visualize/Pythagorean-Forest-stamped.png.webp)

1. 有关输入随机森林模型的信息。
2. 显示参数：
     - `深度`：设置树木生长的深度。
     - `目标类别`：设置为树木着色的目标类别。 如果选择 `无`，则树将为白色。 如果输入是分类树，则可以按节点各自的类别为节点着色。 如果输入是回归树，则选项为 `类均值`，它将通过类均值为树节点着色；以及 `标准差`，它将以节点的标准差值为它们着色。
     - `大小`：设置节点的大小。 `正常` 将使节点保持节点中子集的大小。 *平方根*和*对数*分别是节点大小的变换。
     - `缩放`：允许您查看树可视化文件的大小。
{% include_relative _save_and_report.md %}

## 示例

**毕达哥拉斯森林(Pythagorean Forest)** 非常适合一次可视化几棵已建树。 在下面的示例中，我们使用了 *housing* 数据集，并绘制了使用[随机森林(Random Forest)][随机森林]种植的 10 棵树。 在[随机森林(Random Forest)][随机森林]中更改参数时，**毕达哥拉斯森林(Pythagorean Forest)** 中的可视化效果也会发生变化。

然后，我们在可视化中选择了一棵树，并使用[毕达哥拉斯树(Pythagorean Tree)][毕达哥拉斯树]小部件对其进行了进一步检查。


![](/assets/images/visualize/Pythagorean-Forest-Example.png.webp)

## 参考文献

Beck, F., Burch, M., Munz, T., Di Silvestro, L. and Weiskopf, D. (2014). Generalized Pythagoras Trees for Visualizing Hierarchies. In IVAPP '14 Proceedings of the 5th International Conference on Information Visualization Theory and Applications, 17-28.

{% include _links.md %}