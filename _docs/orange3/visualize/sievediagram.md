---
title: 筛网图(Sieve Diagram)
---

为一对属性绘制一个筛网图。





## 输入
- 数据：输入数据集

## 功能
**筛网图(Sieve Diagram)** 用于可视化双向列联表中的频率并将其与[期望频率](http://cnx.org/contents/d396c4ad-2fd7-47cd-be84-152b44880feb@2/What-is-an-expected-frequency)进行比较。它是 Riedwyl 和 Schüpbach 在 1983 年的一份技术报告中提出的。 在此图中，每个矩形的面积与预期频率成正比，而观察到的频率由每个矩形中的方格数表示。观测频率与预期频率之间的差异（与标准Pearson残差成比例）显示为阴影密度，使用颜色表示与独立性的偏差是正（蓝色）还是负（红色）。

## 界面
![](/assets/images/visualize/SieveDiagram-stamped.png.webp)

1. 选择要在筛图中显示的属性。
2. 分数组合使您能够找到最佳的属性组合。
3. **保存图像** 将创建的图像以 .svg 或 .png 格式保存到您的计算机。
4. 生成报告。

下面的截图显示了 *Titanic* 数据集的筛网图，它具有 *sex* 和 *survived* 属性（后者是该数据集中的类属性）。 该图表明，这两个变量高度相关，因为在所有四个象限中，观察到的频率和预期频率之间存在很大差异。 例如，正如气泡中显示的那样，女乘客幸存下来的机会比预期的要高得多（0.06 比 0.15）。


![](/assets/images/visualize/SieveDiagram-Titanic.png.webp)

具有有趣关联的成对属性具有强烈的阴影，例如上图中所示的图。 为了对比，下面显示了最不重要的一对筛网图（年龄与生存率）。

![](/assets/images/visualize/SieveDiagram-Titanic-age-survived.png.webp)

## 示例
下面，我们看到一个使用 *Titanic* 数据集的简单例子，其中使用
[排名(Rank)][排名]小部件选择最佳属性（具有最高信息增益，增益比率或Gini指数的属性）并将其输入到 **筛网图(Sieve Diagram)** 中。 这将显示两个最佳属性（在我们的案例中是性别和状态）的筛图。 我们看到，泰坦尼克号上的生存率对于头等舱女性而言非常高，而女船员则非常低。

![](/assets/images/visualize/SieveDiagram-Example2.png.webp)

**筛网图(Sieve Diagram)**还具有 `分数组合` 选项，这使属性的排名更加容易。

![](/assets/images/visualize/SieveDiagram-Example1.png.webp)

## 参考文献

Riedwyl, H., and Schüpbach, M. (1994). Parquet diagram to plot contingency tables. In Softstat '93: Advances in Statistical Software, F. Faulbaum (Ed.). New York: Gustav Fischer, 293-299.

{% include _links.md %}