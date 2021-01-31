---
title: 毕达哥拉斯树(Pythagorean Tree)
---

用于分类或回归树的可视化工具。





## 输入
- 树：树模型
- 选定数据：从树中选择的实例

## 功能
**毕达哥拉斯树(Pythagorean Tree)** 是平面分形图像，可用于展示由[Fabian Beck等人](http://publications.fbeck.com/ivapp14-pythagoras.pdf)提出的树层次结构图示。这里，它们用于可视化和浏览[树(Tree)][树]。


## 界面
![](/assets/images/visualize/Pythagorean-Tree1-stamped.png.webp)

1. 有关输入树模型的信息。
2. 可视化参数：
     - `深度`：设置显示树的深度。
     -`目标类别`（用于分类树）：树节点的颜色强度将对应于目标类别的概率。 如果选择 `None` ，则节点的颜色将表示最可能的类别。
     - `节点颜色`（用于回归树）：节点颜色可以对应于节点中训练数据实例的类值的平均值或标准差。
     - `大小`：定义一种方法来计算代表节点的正方形的大小。 `正常` 将使节点大小与节点中训练数据子集的大小相对应。 `平方根` 和 `对数` 分别是节点大小的变换。
     - `对数比例因子选择`在对数转换时才会启用。
3. 绘制属性：
      - `启用工具提示`：悬停时显示节点信息。
      - `显示图例`：显示图的颜色图例。
4. 报告：
     - `保存图像`：将可视化文件保存为SVG或png文件。
     - `报告`：将可视化效果添加到报告中。

毕达哥拉斯树可以可视化分类树和回归树。 以下是回归树的示例。 两者之间的唯一区别是，回归树无法按类别着色，但可以按类别均值或标准差进行着色。

![](/assets/images/visualize/Pythagorean-Tree1-continuous.png.webp)

## 示例
下面的截图中的工作流演示了[查看树(Tree Viewer)][查看树]和 **毕达哥拉斯树(Pythagorean Tree)** 的区别。 它们都可以可视化[树(Tree)][树]，但是 **毕达哥拉斯树(Pythagorean Tree)** 可视化占用的空间更少，并且更紧凑，即使是小的[Iris flower](https://en.wikipedia.org/wiki/Iris_flower_data_set)数据集这种区别也很明显。对于这两个可视化小部件，我们都可以单击控件和可视化区域之间的分隔符来隐藏左侧的控件区域。


![](/assets/images/visualize/Pythagorean-Tree-comparison.png.webp)

**毕达哥拉斯树(Pythagorean Tree)** 是交互式的：单击任何节点（正方形）以选择与该节点关联的训练数据实例。以下工作流程探究了这些功能。


![](/assets/images/visualize/Pythagorean-Tree-scatterplot-workflow.png.webp)

所选数据实例在[散点图(Scatter Plot)][散点图]中显示为子集，发送到[数据表(Data Table)][数据表] 并在[箱线图(Box Plot)][箱线图]中进行检查。 在此示例中，我们使用了 *brown-selected* 的数据集。 树中选定的节点具有黑色轮廓。

![](/assets/images/visualize/Pythagorean-Tree-scatterplot.png.webp)

## 参考文献

Beck, F., Burch, M., Munz, T., Di Silvestro, L. and Weiskopf, D. (2014). [Generalized Pythagoras Trees for Visualizing Hierarchies](http://publications.fbeck.com/ivapp14-pythagoras.pdf). In IVAPP '14 Proceedings of the 5th International Conference on Information Visualization Theory and Applications, 17-28.

{% include _links.md %}