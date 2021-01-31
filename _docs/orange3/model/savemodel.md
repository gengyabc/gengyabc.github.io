---
title: 保存模型(Save Model)
---
将经过训练的模型保存到输出文件。





## 功能
如果文件保存到与工作流相同的目录或该目录的子树中，则该小部件会记住相对路径。 否则，它将存储绝对路径，但出于安全原因禁用自动保存。

## 输入
- 模型：训练过的模型
  
## 界面
![](/assets/images/model/SaveModel-stamped.png.webp)

1. 从以前保存的模型中选择。
2. 使用**浏览**图标保存创建的模型。单击图标，然后输入文件名。该模型将保存到一个 pickled 文件中。
3. 保存模型。

![](/assets/images/model/SaveModel-save.png.webp)


## 示例
当您要保存自定义模型时，请将数据输入模型，然后将其连接到 **保存模型(Save Model)**。 命名模型； 稍后使用[加载模型(Load Model)][加载模型]将其加载到工作流中。 与 [加载模型(Load Model)][加载模型] 一起使用的数据集必须包含兼容的属性。


![](/assets/images/model/SaveModel-example.png.webp)

{% include _links.md %}