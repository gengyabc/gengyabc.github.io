---
title: 多标签识别 (Multi Label Recognition)
---

使用基于腾讯 AI 开放平台的服务进行多标签识别 (腾讯此服务可能不稳定)


## 输入

* 图片路径: 要识别的图片的路径


## 功能
图像多标签识别

## 界面

![](/assets/images/deeplearning/tencent.png.webp)

分别对应腾讯 AI 开放平台的服务的各个参数, 详见[示例](#示例)


## 示例

### 环境准备(已有可跳过)

注册并登录 <https://ai.qq.com/>，进入“控制台”，创建一个新的应用，选择多标签识别，

![](/assets/images/deeplearning/tencent_label.png.webp)

然后接入能力

![](/assets/images/deeplearning/tencent_connect.png.webp)

在“应用管理”的“应用信息”标签，找到 APPID 和 APPKEY，备用。

![](/assets/images/deeplearning/tencent_info.png.webp)

### 实现

设置好之后，在“橙现智能”的“深度学习”模块中找到对应的小部件。在[图片加载器]中选择 “只要预测” 然后载入图片，并可以通过点击“下一组图片”变更图片。在“多标签识别”小部件，输入 `APPID` 和 `APPKEY`，点击“运行”即可看到结果。

![](/assets/images/deeplearning/tencent_workflow.png.webp)


{% include _links.md %}




