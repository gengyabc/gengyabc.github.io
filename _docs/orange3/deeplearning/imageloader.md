---
title: 图片加载器(Image Loader)
---

载入所需图片




## 输出

* 训练数据: 训练数据集
* 测试数据: 测试数据集
* 图片: 导入的单个图片

## 功能
主要为 MNIST 模型载入图片数据, 也可以载入其他图片. 图片会转为灰度图片


## 界面
![](/assets/images/deeplearning/imageloader.png.webp)

1. **图片文件夹**: 要载入的图片数据所在文件夹位置
2. **是否需要训练**: 
   * `需要训练`: 数据文件夹中需要有分别为 "training"和"testing"的文件夹, 二者分别是训练数据和测试数据
   * `只要预测`: 被预测的图片
3. **batch size**
4. **载入图片**: 点击载入图片. 点击可以观察其他批次的图片数据
5. **下一组图片**: 只在选择了`只要预测`后起作用, 可以浏览下一组图片

## 示例

{% include_relative _mnist_workflow.md %}


{% include _links.md %}