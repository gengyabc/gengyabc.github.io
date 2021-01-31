---
title: 马赛克图(Mosaic Display)
---

在马赛克图中显示数据。





## 输入
- 数据：输入数据集
- 数据子集：实例的子集

## 输出
- 选定数据：从图中选择的实例

## 功能
**马赛克图(Mosaic Display)** 是双向频率表或列联表的图形表示。 它用于可视化来自两个或多个定性变量的数据，由 Hartigan 和 Kleiner 于 1981 年引入，并由 Friendly 在 1994 年进行了扩展和完善。它为用户提供了更有效地识别不同变量之间关系的方法。如果您想阅读马赛克图的历史，可以在[这里](http://www.datavis.ca/papers/moshist.pdf)阅读。

## 界面
![](/assets/images/visualize/Mosaic-Display-stamped.png.webp)

1. 选择要查看的变量。
2. 选择内部颜色。您可以根据类别对内部进行着色，也可以使用 *Pearson残差*，它是观测值和拟合值之间的差值，再除以观测值标准偏差的估计值。 如果单击 `与总数比较`，则会对所有实例进行比较。
3. `保存图像` 将创建的图像以 .svg 或 .png.webp 格式保存到您的计算机。
4. 生成报告。


## 示例
我们加载了 *titanic* 数据集，并将其连接到 **马赛克图(Mosaic Display)** 小部件。 我们决定关注两个变量，性别和生存率( sex and survival)。 我们根据 `皮尔逊残差` 对内部进行着色，以证明观察值与拟合值之间的差异。


![](/assets/images/visualize/Mosaic-Display-Example.png.webp)

我们可以看到，男性和女性的生存率明显偏离了拟合值。.
