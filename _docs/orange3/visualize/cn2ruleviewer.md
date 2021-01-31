---
title: CN2 规则查看器(CN2 Rule Viewer)
---

CN2 规则查看




    
## 输入
- 数据：要过滤的数据集
- CN2规则分类器：CN2规则分类器，包括归纳规则的列表

## 输出
- 过滤的数据：所有选定规则覆盖的数据实例

## 功能

显示[CN2分类](https://en.wikipedia.org/wiki/CN2_algorithm)规则的小部件。 如果还连接了数据，则在选择规则时，可以分析哪些实例符合条件。

## 界面
![](/assets/images/visualize/CN2RuleViewer-stamped.png.webp)

1. 可以恢复归纳规则的原始顺序。
2. 当规则很多且很复杂时，视图可能显得很拥挤。 因此，实施了“紧凑视图”，从而可以进行平面展示并更清晰地检查规则。
3. 单击“报告”以显示规则归纳算法及其参数，数据域和归纳规则的详细说明。

此外，选择后，可以通过按默认系统快捷方式（ctrl + C，cmd + C）将规则复制到剪贴板。

## 示例

这里展示小部件的最常用用法。首先，读取数据并训练CN2规则分类器。 我们使用 *titanic* 数据集进行规则构建。然后使用 **CN2 规则查看器(CN2 Rule Viewer)** 查看规则。要探索不同的 CN2 算法并了解调整参数如何影响学习过程，应在设置 CN2 学习算法的同时保持 **CN2 规则查看器(CN2 Rule Viewer)** 打开并可见。

![](/assets/images/visualize/CN2-Viewer-Example1.png.webp)

选择规则将输出过滤后的数据实例。 这些可以在[数据表(Data Table)][数据表]中查看。

{% include _links.md %}