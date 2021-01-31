---
title: 多元线性回归 -- 特征工程
---

上一部分通过[使用散点图探索], 我们对数据有了更深入的了解, 这一部分我们就在此基础上, 做一下特征工程.





## 介绍
我们这里尝试构造一个新的特征, 看看会不会对模型产生什么影响.


## 视频教程

{% include video id="BV1N7411t7j3" provider="bilibili" danmaku="1" page="4"%}

## 构造宿舍特征

这里要使用[特征构造器]构造所需要的特征. 点击 **变量定义** 框中的 **新建** 下拉框, 选择 `分类数据`

![](/assets/images/tutorial/mlr-feature1.png.webp)


然后对照下图, 输入新特征名称 `apartment`, 取值有 1 和 0. 条件为 `1 if bedrooms > 6 else 0`. 可选值为 `1, 0`
![](/assets/images/tutorial/mlr-feature2.png.webp)

> 特征名称不会写的话,可以使用 **选择特征** 下拉菜单选择特征.

点击 **发送** 就可以输出添加了新特征的数据了. 保险起见, 我们可以在[数据表]中查看这个新特征. 确定新特征有正确的分类值.

![](/assets/images/tutorial/mlr-workflow2.png.webp)

> 新建分类属性的值可能和预期的不一样. 比如这里可能本来预计 `bedrooms > 6` 是 1, 其他的为 0, 但是数据表中却是相反的, 这个关系不大, 可以不管它. 

新的数据集连接另一个[测试与评分]后, 可以发现模型没有太大变化.

![](/assets/images/tutorial/mlr-workflow3.png.webp)



## 构造豪宅特征
接下来我们根据经纬度构造豪宅特征. 如下图所示, 建立新的分类特征, 特征条件是 `1 if 47.5<lat<47.65 and -122.4<long<-122.1 else 0`.

我们发现, 现在 R2 有了较大的提高, 说明这个特征不错.


![](/assets/images/tutorial/mlr-workflow4.png.webp)


## 其他处理

### 归一化
类似线性回归这样与几何特征有关的算法都应该进行归一化处理. 如下图连接一个[预处理器]和[测试与评分]. 使用 **归一化特征**, 可以发现[测试与评分]结果没有什么太大变化.

![](/assets/images/tutorial/mlr-workflow5.png.webp)

### 数值特征还是分类特征

此数据集有一个数据, 橙现智能默认为 **数值数据**, 但是这样好吗?

在[文件]小部件中, 设置如下特征为 **分类特征**

![](/assets/images/tutorial/mlr-file.png.webp)

可以发现[测试与评分]结果有了较大提高.

![](/assets/images/tutorial/mlr-test.png.webp)


## 小结
通过基于探索性数据分析的特征工程和其他流程化的特征工程技术, 我们将模型的性能提高了不少, 有兴趣的朋友请继续试试, 看看有没有更好的结果. 下一部分, 我们继续[优化模型和模型解释](../05mlr-exp/)

## 资源下载
* [工作流](/assets/workflows/2020/mlr.ows)
* [数据]



[使用散点图探索]: ../tutorial/03mlr/
[数据]: https://share.weiyun.com/NfiPyK5V
{% include _links.md %}
