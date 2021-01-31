---
title: 多元线性回归 -- 使用散点图探索
---

通过上一部分[简单线性回归]了解了橙现智能的基本使用方法后, 我们开始一个复杂一些的任务, 多元线性回归.




## 介绍
此任务中我们使用 **kaggle** [房价预测](https://www.kaggle.com/harlfoxem/housesalesprediction/home)的例子以及其数据来进行多元线性回归实战。这里给出了 19 个房屋特征，附加一个 id 列，目的是预测有了新房的话，根据房屋特征判断房价（price）是多少。比赛总共提供了 21613 个样本。数据及其说明都在比赛网站可见, 也可以直接下载此[数据]。此任务我们使用“橙现智能”实现。

## 视频教程
{% include video id="BV1N7411t7j3" provider="bilibili" danmaku="1" page="3"%}


## 基准工作流

和[简单线性回归]一样, 搭建如下工作流, 并可以在[测试与评分]中查看结果. 此部分不再详述.
![](/assets/images/tutorial/lr-base-workflow.png.webp)

> 此处唯一注意的就是要使用 *kc_house_data.csv* 这个[数据], 并且设置 *price* 为 `目标`

![](/assets/images/tutorial/mlr-loaddata.png.webp)

此时的`R2`大概是 0.7 左右. 下一步我们尝试将此数值提高.

## 探索性数据分析

### 卧室
可以使用[数据表]查看, 很难看出什么. 接着继续使用[散点图]进一步分析.

![](/assets/images/tutorial/mlr-workflow1.png.webp)

此散点图结果显示的是 *price* 与 *bedrooms* (价格与卧室数量)的关系. 我们可以发现卧室数量在 6 附近的时候房价最高, 随后会有下降. 这就是一个比较奇怪的现象了, 为什么会这样呢? 通过猜测, 我们假设卧室数量过多的话, 可能就是宿舍一类的房子了, 价格应该不高. 这样的话, 这类房子的大小应该也不大, 我们可以通过观察 *sqft_living* 与 *bedrooms* 关系来看, 卧室数量过多的房屋的确可能是宿舍. 

![](/assets/images/tutorial/mrl-scatter1.png.webp)

我们可以在散点图看到 *price* 和 *sqft_living* 有很好的线性关系, 可以感觉到, [散点图]查看数据很不错.
![](/assets/images/tutorial/mrl-scatter2.png.webp)

### 经纬度
有了这个猜想后, 我们再看看其他特征, 比如经纬度.

这里我们将 x 和 y 轴更改为了 *lat* 和 *long*, 为了查看方便, 反选了 `显示图例`(因为我已经知道**黄色的价格高**). 这样, 我们发现, 在图中间隐约有一个豪宅区.

![](/assets/images/tutorial/mrl-scatter3.png.webp)


### 其他探索
这里就不再探寻其他特征了, 有兴趣请自己试试探索.

## 小结
本部分实现了多元线性回归的基准工作流, 并且使用散点图探索了各个特征, 下一步就要在此基础上进行[特征工程](../04mlr_feature/)了

## 资源下载
* [工作流](/assets/workflows/2020/mlr.ows)
* [数据]

[简单线性回归]: ../02linear_regression/
[数据]: https://share.weiyun.com/NfiPyK5V
{% include _links.md %}

