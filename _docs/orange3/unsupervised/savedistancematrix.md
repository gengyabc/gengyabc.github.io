---
title: 保存距离矩阵(Save Distance Matrix)
---
保存距离矩阵。






如果文件保存到与工作流相同的目录或该目录的子目录中，则该小部件会记住相对路径。 否则，它将存储绝对路径，但出于安全原因禁用自动保存。


## 输入

- 距离：距离矩阵


## 界面
![](/assets/images/unsupervised/SaveDistanceMatrix-stamped.png.webp)

1.单击**保存**，从以前保存的距离矩阵中选择。 或者，勾选 **保存** 按钮左侧的框，更改将 **自动发送**。
2.单击 **另存为**，即可将距离矩阵保存到计算机，只需输入文件名，然后单击 **另存为**。 距离矩阵将保存为 **.dst** 类型。


## 示例

我们使用[距离变换(Distance Transformation)][距离变换] 小部件来转换 *Iris* 数据集中的距离。然后，我们选择将转换后的版本保存到我们的计算机中，以便稍后使用。我们决定输出所有数据实例。您可以选择仅输出数据矩阵的一小部分。 如果您想知道更改文件的内容，请参阅[距离文件(Distance File)][距离文件].



![](/assets/images/unsupervised/SaveDistanceMatrix-Example.png.webp)

{% include _links.md %}