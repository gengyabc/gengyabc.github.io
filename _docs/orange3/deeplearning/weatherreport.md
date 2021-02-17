---
title: 天气播报(Weather Report)
---

使用百度自然语言处理平台实现天气播报





## 功能
我们体验一下智能创作，使用百度的自然语言处理的[智能创作平台](https://cloud.baidu.com/doc/NLP/s/ik3hbjj0v)，自动生成一个天气播报。

## 界面

![](/assets/images/deeplearning/weatherreport.png.webp)

分别对应[智能创作平台](https://cloud.baidu.com/doc/NLP/s/ik3hbjj0v)的各个参数, 详见[示例](#示例)


## 示例

### 环境准备(已有可跳过)
首先登陆平台 <https://login.bce.baidu.com/>。如果没有账号的话，可以免费注册。登陆之后点击页面左上角的“产品服务”， 找到“智能创作平台”

![](/assets/images/deeplearning/baidu.png.webp)

点击“创建应用”

![](/assets/images/deeplearning/baidu_createapp.png.webp)

在出现的页面中填写提示的信息，然后创建应用即可

![](/assets/images/deeplearning/baidu_create_ok.png.webp)

然后在应用列表中，出现应用信息，这些信息在后面的工作中会用到。

![](/assets/images/deeplearning/baidu_info.png.webp)

接着点击“我的写作项目”按钮，新页面中点击“十字叉”创建新的项目

![](/assets/images/deeplearning/baidu_proj.png.webp)

然后选择“自动创作”，再选择“天气预报推送”即可

![](/assets/images/deeplearning/baidu_auto.png.webp)

![](/assets/images/deeplearning/baidu_type.png.webp)

在项目列表页面，点击项目卡片的“查看生成记录”

![](/assets/images/deeplearning/baidu_check_info.png.webp)

在出现的页面中，找到“项目 ID” 备用

![](/assets/images/deeplearning/baidu_id.png.webp)

### 开始播报

在“橙现智能”中的深度学习模块，找到“天气播报”小部件。在输入框中输入对应的内容，点击“运行”即可看到对应信息的天气播报。

![](/assets/images/deeplearning/baidu_report.png.webp)
