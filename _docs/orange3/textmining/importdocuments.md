---
title: 文件夹载入(Import Documents)
redirect_from:
    - /docs/orange3/text/importdocuments/
---

从文件夹中导入文本文档。




## 输出
- 语料库: 本地机器上的文件集合。

## 功能
**文件夹载入**小部件从文件夹中检索文本文件并创建一个语料库。小工具读取 .txt、.docx、.odt、.pdf和.xml等文件。如果一个文件夹包含子文件夹，它们将被用作类别标签。

## 界面
![](/assets/images/text/Import-Documents-stamped.png.webp)

1. 正在加载的文件夹。
2. 从本地机器加载文件夹。
3. 重新加载数据。
4. 检索的文件数量。
   

如果小组件因某种原因无法读取文件，则将跳过该文件。成功检索的文件仍将在输出中。

## 示例

要检索数据，选择小部件右侧的文件夹图标。选择您希望转为语料库的文件夹。加载完成后，您将看到检索到的文档数量。要检查它们，请将小组件连接到 [语料查看器]。我们使用了一组纯文本格式的肯尼迪的演讲稿。

![](/assets/images/text/Import-Documents-Example1.png.webp)

现在让我们用子文件夹试试。我们把肯尼迪的演讲放在两个文件夹中--1962年以前和1962年以后。如果我加载父文件夹，这两个子文件夹将被用作类标签。检查[数据表]中此小部件的输出。

![](/assets/images/text/Import-Documents-Example2.png.webp)

{% include _links.md %}
