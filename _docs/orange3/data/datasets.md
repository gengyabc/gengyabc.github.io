---
title: "数据集(Datasets)"
---

从在线存储库加载数据集。




## 输出
- 输出数据:数据集

## 功能

此小部件从服务器检索选定的数据集，并将其发送到输出。文件下载到本地就可以使用了，之后使用无需联网。每个数据集都提供了关于数据大小、实例数量、变量数量、目标和标签的描述和信息。

![](/assets/images/data/Datasets-stamped.png.webp)

## 界面
1. 可用数据集的内容。描述每个数据集实例和变量的大小、数量、目标变量的类型和标签。
2. 数据集描述。

## 例子
橙现智能工作流程可以以 **数据集(Datasets)** 小部件开始而非 [文件(File)][文件] 小部件开始。在下面的示例中，小部件可以于在线数据库(Kickstarter数据)检索数据集，然后将数据集发送到 [数据表(Data Table)][数据表] 和 [分布(Distributions)][分布]。

![](/assets/images/data/Datasets-Workflow.png.webp)

{% include _links.md %}