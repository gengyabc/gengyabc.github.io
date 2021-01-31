---
title: 查看树(Tree Viewer)
---

分类树和回归树的可视化。





## 输入
- 树：决策树

# 输出
- 选定数据：从树节点中选择的实例
- 数据：带有附加列的数据，显示是否选择了一个点

## 功能
这是一个多功能的小部件，可进行[分类和回归树](https://en.wikipedia.org/wiki/Decision_tree_learning)的二维可视化。 用户可以选择一个节点，指示小部件输出与该节点关联的数据，从而进行探索性数据分析。

## 界面
![](/assets/images/visualize/TreeViewer-stamped.png.webp)

1. 输入信息
2. 显示选项:
    - 放大和缩小
    - 选择树的宽度。节点悬停在节点上时会显示信息气泡。
    - 选择树的深度。
    - 选择边缘宽度。根据选定的边缘宽度绘制树图中节点之间的边缘。  
       - 如果选择 `固定`，则所有边缘的宽度相等。
       - 选择 `相对于根` ，边缘的宽度将对应实例在训练数据中所有实例的比例。这样树底部的边将变得越来越窄。
       - `相对于父级` 使边缘宽度与父节点数据成比例。
    -定义目标类别，您可以根据数据中的类别进行更改
3. 按 **保存图像** 将创建的树形图以 *.svg* 或者 *.png* 文件保存到您的计算机。
4. 生成报告。

## 示例

下面是一个简单的分类方案，我们在其中读取数据，构造决策树并在 **查看树(Tree Viewer)** 中查看它。 如果 **查看树(Tree Viewer)** 和[树(Tree)][树]都打开，则重新运行树算法将立即影响可视化。因此，您可以使用此组合来探索算法的参数如何影响结果树的结构。

![](/assets/images/visualize/TreeViewer-classification.png.webp)

单击任何节点将输出相关的数据实例。下面的探索使用[散点图(Scatter Plot)][散点图]查看的子集。确保树数据作为数据子集传递；这可以通过以下方法完成：首先将[Scatter Plot][散点图]连接到[文件(File)][文件] 小部件，然后将其连接到 **查看树(Tree Viewer)** 小部件。 所选数据将显示为粗体点。

**查看树(Tree Viewer)** 也可以导出标记过的数据。将[数据表(Data Table)][数据表]连接到**查看树(Tree Viewer)**，并将小部件之间的链接设置为 **数据**，而不是 **选中的数据**。这会将整个数据发送到 [数据表(Data Table)][数据表]，并带有一个附加的元列，这个列标记了选定的数据实例（对于选定的数据实例为 *是*，对于其余的实例为 *否*）。

![](/assets/images/visualize/TreeViewer-selection.png.webp)

最后，**查看树(Tree Viewer)** 也可用于可视化回归树。 使用 *housing.tab* 数据集将[随机森林(Random Forest)][随机森林]连接到[文件(File)][文件]小部件。 然后将[毕达哥拉斯森林(Pythagorean Forest)][毕达哥拉斯森林]连接到 [随机森林(Random Forest)][随机森林]。 在[毕达哥拉斯森林(Pythagorean Forest)][毕达哥拉斯森林]中，选择您想要进一步分析的回归树，并将其传递给 **查看树(Tree Viewer)**。 小部件将显示构造的树。要可视化较大的树，尤其是对于回归而言，[毕达哥拉斯树(Pythagorean Tree)][毕达哥拉斯树]可能是更好的选择。

![](/assets/images/visualize/TreeViewer-regression.png.webp)

{% include _links.md %}