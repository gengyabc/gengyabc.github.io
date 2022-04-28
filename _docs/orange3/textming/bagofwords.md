---
title: 词袋(Bag of Words)
---

从输入的语料库中生成一个词袋。





## 输入

- 语料库: 文件集。

## 输出

- 语料库: 附加了词袋特征的语料库。

## 功能
**词袋**模型为每个数据实例（文档）创建了一个带有各个词数量的语料库。词数可以是绝对数、二进制数（包含或不包含）或次线性数（词频的对数）。词袋模型与[词充实]结合使用，可用于预测性建模。

## 界面
![](/assets/images/text/Bag-of-Words-stamped.png.webp)

1. [词袋](https://en.wikipedia.org/wiki/Tf%E2%80%93idf)模型的参数。
    - 词频。
        - `个数`：一个词在文档中出现的次数。
        - `二进制`：文档中出现或不出现单词。
        - `个数的对数`：词频的对数
    - 文件频率：
        - (none)
        - IDF: [逆文档频率](http://nlp.stanford.edu/IR-book/html/htmledition/inverse-document-frequency-1.html)
        - [平滑IDF](http://scikit-learn.org/stable/modules/generated/sklearn.feature_extraction.text.TfidfTransformer.html)：在文件频率上加一，防止零除。
    - 正则化。
        - (无)
        - L1（元素之和）：将向量长度归一化为元素之和。
        - L2(欧氏)：将向量长度归一化为平方和。
2. 制作一份报告。
3. 如果**自动发送**开启，则会自动传达更改。或者按 **发送**。


## 示例

在第一个例子中，我们将简单地检查词袋模型的大概。用[语料库]小部件加载*book-excerpts.tab*，并将其连接到**词袋**。这里我们保留了默认值 -- 一个简单的词频计数。检查**词袋**在[数据表]输出的内容。最后一列白色的是代表每个文档的词频。


![](/assets/images/text/Bag-of-Words-Example1.png.webp)

在第二个例子中，我们将尝试预测文档类别。我们仍然使用 *book-excerpts.tab* 数据集，我们通过[文本预处理]发送默认参数。然后我们将[文本预处理]连接到**词袋**，获得词频，我们将通过这个频率来计算模型。


![](/assets/images/text/Bag-of-Words-Example2.png.webp)

将**词袋**连接到[测试与评分]进行预测建模。将[支持向量机] (SVM)或任何其他分类器也连接到[测试与评分]（都在左侧）。现在，[测试与评分]将为每个学习器计算输入的性能分数。在这里，我们用 SVM 得到了相当令人印象深刻的结果。现在我们可以检查，模型在哪里犯了错误。

在[测试与评分]中添加[混淆矩阵]。混淆矩阵显示正确和错误的分类文档。选择**错误分类**会输出错误分类的文档，我们可以用[语料查看器]进一步检查。

{% include _links.md %}