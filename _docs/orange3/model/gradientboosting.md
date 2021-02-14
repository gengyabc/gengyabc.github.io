---
title: 梯度提升(Gradient Boosting)
---

在决策树上使用梯度提升进行预测。





## 输入
- 数据：输入数据集
- 预处理器：预处理方法

## 输出
- 学习器：梯度提升学习算法
- 模型：训练过的模型

## 功能
[梯度提升](https://en.wikipedia.org/wiki/Gradient_boosting) 是用于回归和分类问题的机器学习技术，它集成一组弱预测模型（通常为决策树）生成预测模型。

除了 `Gradient Boosting (scikit-learn)`, 其他所有算法需要自己[手动安装](#安装方法)

## 界面
![](/assets/images/model/GradientBoosting-stamped.png.webp)


1. 指定模型名称。 默认名称是“梯度提升(Gradient Boosting)”。
2. 选择一种梯度提升算法：
   - [Gradient Boosting (scikit-learn)](https://scikit-learn.org/stable/modules/generated/sklearn.ensemble.GradientBoostingClassifier.html)
   - [Extreme Gradient Boosting (xgboost)](https://xgboost.readthedocs.io/en/latest/index.html)
   - [Extreme Gradient Boosting Random Forest (xgboost)](https://xgboost.readthedocs.io/en/latest/index.html)
   - [Gradient Boosting (catboost)](https://catboost.ai/docs/concepts/python-quickstart.html)
3. 基本属性：
    - `树数量`：指定将包含多少棵梯度增强树。通常，数量多会导致更好的性能。
    - `学习率`：指定提升的学习率。学习率缩小每棵树的贡献。
    - `可重复训练`：固定随机种子，从而使结果可复制。
    - `正则化`：指定 L2 正则化项。 仅适用于 *xgboost* 和 *catboost* 方法。
4. 生长控制：
    - `限制单个树深度`：指定单个树的最大深度。
    - `不要分割小于...的子集`：指定可以分割的最小子集。 仅适用于 *scikit-learn* 方法。
5. 下采样：
    - `训练实例的比例`：指定拟合单个树的训练实例的百分比。 适用于 *scikit-learn* 和 *xgboost* 方法。
    - `每棵树的特征比例`：指定构造每棵树时使用的特征百分比。 适用于 *xgboost* 和 *catboost* 方法。
    - `每层的功能比例`：指定每层使用的特征百分比。 仅适用于 *xgboost* 方法。
    - `每个分割的特征比例`：指定每个分割使用的特征百分比。 仅适用于 *xgboost* 方法。
{% include_relative _report_apply.md %}


## 示例
对于分类任务，我们使用 *heart disease* 数据。 在这里，我们比较[测试与评分]小部件中的所有可用方法。

![](/assets/images/model/GradientBoosting-example.png.webp)

{% include _links.md %}

## 安装方法

{% include _install_others.md %}