---
title: 随机化(Randomize)
---
将输入数据集的类别、属性和(或)元无序化

## 输入
- 数据:输入数据集

## 输出
- 数据: 随机化的数据集

## 功能
**随机化(Randomize)** 小部件在输入端接收数据集，并输出相同的数据集，但是其中的类、属性和(或)会被被随机排列。

## 界面

![](/assets/images/data/Randomize-Default.png.webp)

1. 选择要混排的数据集的列将被如何分组。
2. 选择要被混排的数据集的比例。
3. 产生一个可以复制混排输出。
4. 如果勾选了自动发送，则小部件会自动将更改传达给其他小部件。

## 示例
**随机化(Randomize)** 小部件通常放在数据输出之后(右)（例如[文件(File)][文件]小部件）。下图示例展示了其基本用法，可以看到 **iris** 数据集的类变量值被随机排列了。

![](/assets/images/data/Randomize-Example1.png.webp)

在下面的示例中，我们将演示对类变量值进行随机排列将会如何影响上面展示的同一数据集上模型的性能。

![](/assets/images/data/Randomize-Example2.png.webp)

{% include _links.md %}

