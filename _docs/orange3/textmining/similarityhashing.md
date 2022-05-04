---
title: 相似哈希(Similarity Hashing)
redirect_from:
    - /docs/orange3/text/similarityhashing/
---

计算文件的哈希值。





## 输入

- 语料库: 文件集。

## 输出

- 语料库: 以simhash值为属性的语料库。

## 功能
**相似哈希(Similarity Hashing)**是一个将文档转化为相似性向量的小工具。这个小工具使用Moses Charikar的[SimHash](https://en.wikipedia.org/wiki/SimHash)方法。

## 界面

![](/assets/images/text/Similarity-Hashing-stamped.png.webp)

1. 设置Simhash大小（输出上会有多少属性，对应信息bit 数）和shingle长度（一个shingle中使用多少个tokens）。
2. 按**自动发送**自动输出数据。或者，按**发送**。


## 示例

我们将使用 *deerwester.tab* 来查找这个小语料库中的相似文档。用[语料库]小部件加载数据，并将其传递给**相似哈希(Similarity Hashing)**。我们将保持默认的哈希大小和shingle长度。我们可以观察小部件在[数据表]中输出的内容。有64个新属性可用，对应*Simhash大小* 参数。



![](/assets/images/text/Similarity-Hashing-Example.png.webp)

## 参考文献

Charikar, M. (2002) Similarity estimation techniques from rounding algorithms. STOC '02 Proceedings of the thirty-fourth annual ACM symposium on Theory of computing, p. 380-388.

{% include _links.md %}