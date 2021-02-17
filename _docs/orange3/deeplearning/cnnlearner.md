---
title: 卷积神经网络学习器(CNN Learner)
---

设置一个简单的卷积神经网络学习器




## 输出: 
* CNN 模型: 配置好的 CNN 模型超参数

## 功能
构建一个训练 MNIST 数据集的简单卷积神经网络

默认一个 5 层网络, 用于构建一个训练 MNIST 数据集的简单卷积神经网络. 每层结构为:

```python
nn.Conv2d(ni, nf, kernel_size=3, stride=2, padding=1)
```

即固定滤波器大小 3, 步幅为 2, 填充为 1. 用户只需要设置每层的输出通道数目.

## 界面

![](/assets/images/deeplearning/cnnlearner.png.webp)


* 设置每层输出通道数目
* **观察并输出模型**: 将模型结构显示在右侧, 并输出模型设置

## 示例

{% include_relative _mnist_workflow.md %}


{% include _links.md %}