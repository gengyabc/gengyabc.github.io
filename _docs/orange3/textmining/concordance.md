---
title: 词上下文(Concordance)
redirect_from:
    - /docs/orange3/text/concordance/
---
显示该词的上下文。




## 输入

- 语料库: 文件集。

## 输出

- 选定的文件。含有查询词的文件。
- 上下文

## 功能
**词上下文(Concordance)**在文本中找到被查询的单词，并显示该单词的上下文。一种颜色的结果来自同一文档。小组件可以输出选定的文档以进行进一步分析，或输出查询词的表。请注意，该小组件只查找完全匹配的单词，这意味着如果您查询 "do "这个单词，结果中不会出现 "doctor"这个单词。

## 界面
![](/assets/images/text/Concordance-stamped.png.webp)
1. **信息**：
   - 文档：输入的文件数。
   - 词：输入端的词数量。
   - 类型：输入端唯一的词数量。
   - 匹配：包含查询词的文档数。
2. **显示前后词数目**：查询词每边显示的字数。
3. 被查询的词。
4. 如果**自动提交**开启，则自动传达所选文档。或者按*提交*。

## 示例

**词上下文(Concordance)** 可以用于显示语料库中的单词上下文。首先，我们在[语料库]中加载 *book-excerpts.tab*。然后，我们将[语料库]连接到 **词上下文(Concordance)**，搜索 "doctor"一词的上下文。小工具会显示所有包含 "doctor"这个词的文档以及它们的周边（上下文）词。

现在，我们可以选择那些包含有趣上下文的文档，并将其输出到 [语料查看器]以进一步检查它们。

![](/assets/images/text/Concordance-Example1.png.webp)

在第二个例子中，我们将输出上下文。我们将保留 [语料库] 中的 *book-excerpts.tab* 及其与 **词上下文(Concordance)** 的连接。我们的查询词仍然是'doctor'。

这次，我们将把[数据表]连接到**词上下文(Concordance)**，并选择输出为**上下文(Concordance)**。在[数据表]中，我们得到了一个查询词和对应文档的列表。现在，我们将用[保存数据]小部件保存这个表，这样我们就可以在其他项目中使用它，或者进行进一步的分析。

![](/assets/images/text/Concordance-Example2.png.webp)

{% include _links.md %}
