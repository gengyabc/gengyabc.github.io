---
title: 分布(Distributions)
---

显示单个属性的值分布。





## 输入

- 数据：输入数据集

## 功能
**分布(Distributions)** 小部件显示离散或连续属性值的[分布](https://en.wikipedia.org/wiki/Frequency_distribution)。如果数据包含分类变量，则分布可以以其为分类条件

对于离散属性，小部件显示的图形会显示每个属性值出现在数据中的次数（例如，在多少个实例中）。如果数据包含分类变量，则还将显示每个属性值的分类分布（如下面的截图所示）。为了创建该图，我们使用了 *Zoo* 数据集。

<!-- TODO: 不一致 -->
## 界面
![](/assets/images/visualize/Distributions-Disc-stamped.png.webp)

1. 分布显示的变量列表
~~2. 如果选中* Bin连续变量*，小部件将通过将它们分配给间隔来离散化连续变量。 间隔数由精度标尺设置。 另外，您可以为连续变量的分布曲线设置平滑度。~~
~~3. 可能要求窗口小部件仅显示某些类（* Group by *）的实例的值分布。 *显示相对频率*将按数据集的百分比缩放数据。~~
4. 显示概率。
5. **保存图像** 将图形以 *.svg* 或 *.png* 格式保存到计算机中。
6.生成报告。

对于连续属性，属性值显示为函数图。连续属性的分类概率是通过高斯核密度估计获得的

出于本示例的目的，我们使用了 *Iris* 数据集。

![](/assets/images/visualize/Distributions-Cont.png.webp)

如果没有分类数据，条形显示为灰色。 我们使用了 *Housing* 数据集。

![](/assets/images/visualize/Distributions-NoClass.png.webp)

