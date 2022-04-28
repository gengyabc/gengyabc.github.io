---
title: 文档地图(Document Map)
---

显示文本中提到的地理位置。





## 输入

- 数据: 数据集。

## 输出

- 语料库: 有提及选定地理区域的文件。

## 功能
**文档地图**小工具从文本（字符串）数据中显示地理位置。它能找到地理名称（国家和首都）的提及，并在地图上显示这些名称的分布（提及频率）。它适用于任何输出数据表并包含至少一个字符串属性的小部件。该小部件输出选定的数据实例，即所有包含提及选定国家（或多个国家）的文件。

## 界面
![](/assets/images/text/DocMap-stamped.png.webp)

1. 选择您要搜索地理位置的元属性。小工具将查找文本中所有提及地理位置的内容，并在地图上显示分布情况。
2. 选择您希望显示的地图类型。选项是`世界`、`欧洲`和`美国`。您可以通过按地图上的 `+` 和 `-` 按钮或鼠标滚动来放大和缩小地图。
3. 数据地理分布的图例。在选定的区域属性中，颜色最重的国家最常被提及（频率最高）。


要选择提到特定国家的文档，请点击一个国家，小组件将输出匹配的文档。要选择多个国家，请在选择时按住Ctrl/Cmd。

## 示例

~~~**Document Map** widget can be used for simply visualizing distributions of geolocations or for a more complex interactive data analysis. Here, we've queried [NY Times](nytimes.md) for articles on Slovenia for the time period of the last year (2015-2016). First we checked the results with [Corpus Viewer](corpusviewer.md).~~~

![](/assets/images/text/DocMap-Example.png.webp)

<!-- Then we sent the data to **Document Map** to see distributions of geolocations by *country* attribute. The attribute already contains country tags for each article, which is why **NY Times** is great in combinations with **Document Map**. We selected Germany, which sends all the documents tagged with Germany to the output. Remember, we queried **NY Times** for articles on Slovenia.

We can again inspect the output with **Corpus Viewer**. But there's a more interesting way of visualizing the data. We've sent selected documents to [Preprocess Text](preprocesstext.md), where we've tokenized text to words and removed stopwords.

Finally, we can inspect the top words appearing in last year's documents on Slovenia and mentioning also Germany with [Word Cloud](wordcloud.md). -->

{% include _links.md %}
