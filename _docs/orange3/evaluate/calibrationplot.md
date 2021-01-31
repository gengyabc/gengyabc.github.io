---
title: 校准图(Calibration Plot)
---

显示分类器的概率预测与实际分类概率之间的匹配。.






## 输入

- 评估结果：测试分类算法的结果

## 功能
[校准图(Calibration Plot)](https://en.wikipedia.org/wiki/Calibration_curve)根据分类器预测的概率绘制类别概率。


## 界面
![](/assets/images/evaluate/CalibrationPlot-stamped.png.webp)

1. 从下拉菜单中选择所需的目标类别。
2. 选择要绘制的分类器。对角线代表最佳行为；分类器的曲线越近，其预测概率越准确。因此，我们将使用此小部件来查看分类器是过于乐观（主要给出积极的结果）还是悲观的（主要给出负面的结果）。
~~3. 如果启用了* Show rug *，则图的底部和顶部将显示刻度线，分别代表负例和正例。它们的位置与分类器的概率预测相对应，颜色显示分类器。在图的底部，左侧的点是（正确）分配给目标类别的低概率的点，右侧的点是错误地分配了高概率的点。在图的顶部，正确分配了右侧的实例高概率，反之亦然。~~
4. 如果要将创建的图像以.svg或.png格式保存到计算机，请按*保存图像*。
5. 生成报告。


## 示例
目前，唯一可以提供 **校准图(Calibration Plot)** 所需信号类型的窗口小部件是[测试与评分(Test & Score)][测试与评分]。 因此，**校准图(Calibration Plot)** 肯定连在 [测试与评分(Test & Score)][测试与评分] 后面。

这是一个典型的示例，其中我们比较了三个分类器: [朴素贝叶斯(Naive Bayesian)][朴素贝叶斯]，[树(Tree)][树]和[常量预测(Constant)][常量预测]，然后将其输入 [测试与评分(Test & Score)][测试与评分] 。 我们使用了 *Titanic* 数据集。 然后，[测试与评分(Test & Score)][测试与评分] 将显示每个分类器的评估结果。 然后，我们从 [测试与评分(Test & Score)][测试与评分] 中绘制 **校准图(Calibration Plot)** 和[ROC 分析(ROC Analysis)][ROC 分析]小部件，以进一步分析分类器的性能。 借助 **校准图(Calibration Plot)** ，您可以查看图中类概率的预测准确性。


![](/assets/images/evaluate/CalibrationPlot-example.png.webp)

{% include _links.md %}
