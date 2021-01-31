---
title: 支持向量机(SVM)
---

支持向量机将输入映射到高维特征空间。






{% include_relative _input.md%}

## 输出

- 学习器：SVM 学习算法
- 模型：训练过的模型
- 支持向量: 用作支持向量的数据点


## 功能
[支持向量机](https://en.wikipedia.org/wiki/Support_vector_machine)（SVM）是一种机器学习技术，它用超平面分隔特征空间，从而最大程度地提高了不同分类之间的边界。该技术通常会产生极高的预测性能。橙现智能从[LIBSVM](https://www.csie.ntu.edu.tw/~cjlin/libsvm/)包中嵌入了 `SVM` 的流行实现。该小部件是其图形用户界面。

对于回归任务，**SVM** 使用 *ε* 不敏感损失在高维特征空间中执行线性回归。其估计精度取决于C，ε和核参数的良好设置。 窗口小部件基于[SVM回归](https://en.wikipedia.org/wiki/Support_vector_machine#Regression)输出类别预测。

该小部件可用于分类和回归任务。


## 界面
![](/assets/images/model/SVM-stamped.png.webp)

1. 给学习器一个名称，该名称将出现在其他小部件中。默认名称是“支持向量机(SVM)”。
2. 具有测试错误设置的SVM。 *SVM*和 *ν-SVM* 基于误差函数的不同最小化。您可以设置测试错误方法：
   - [SVM](http://scikit-learn.org/stable/modules/generated/sklearn.svm.SVR.html)：
      -[损失](http://www.quora.com/What-are-C-and-gamma-with-regards-to-a-support-vector-machine)：即惩罚，适用于分类和回归任务。
      -ε：ε-SVR 模型的参数，适用于回归任务。定义与真实值的距离，在该距离内没有惩罚与预测值相关联。
   - [ν-SVM](http://scikit-learn.org/stable/modules/generated/sklearn.svm.NuSVR.html#sklearn.svm.NuSVR)：
      - [损失](http://www.quora.com/What-are-C-and-gamma-with-regards-to-a-support-vector-machine)：即惩罚，仅适用于回归任务
      - ν：ν-SVR 模型的参数，适用于分类和回归任务。训练误差分数的上限，支持向量分数的下限。

3. 核是一种将特征空间转换为新的特征空间以适合最大边距超平面的函数，从而允许算法使用[线性](https://en.wikipedia.org/wiki/Linear_model)创建模型，[多项式](https://en.wikipedia.org/wiki/Polynomial_kernel)，[RBF](https://en.wikipedia.org/wiki/Radial_basis_function_kernel)和[Sigmoid](http://crsouza.com/2010/03/kernel-functions-for-machine-learning-applications/#sigmoid)核。选择核时会显示指定核函数，其中涉及的常量为：
   - `g` 表示核函数中的 `gamma` 常数（建议值为 1/k，其中 k 为特征的数量，但是由于可能没有给小部件提供训练集，因此默认值为0，并且用户必须手动设置此选项），
   - `c` 表示核函数中的常数c0（默认为0），并且
   - `d` 表示核的等级（默认为3）。
4. 在 **“数值公差”** 中设置与期望值的允许偏差。选中 **迭代极限** 旁边的框，以设置允许的最大迭代次数。

{% include_relative _report_apply.md %}

## 示例

在第一个（回归）示例中，我们使用了 *housing* 数据集，并使用 [数据采样器(Data Sampler)][数据采样器] 将数据分为两个数据子集: **数据样本** 和 **剩余数据**。 样本被发送到 SVM 生成一个 **模型**，然后将其用于[预测(Predictions)][预测]中以预测 **剩余数据** 中的值。如果数据已经在两个单独的文件中，则可以使用类似的架构。 在这种情况下，将使用两个[文件(File)][文件]小部件代替[文件(File)][文件]- [数据采样器(Data Sampler)][数据采样器] 组合。

![](/assets/images/model/SVM-Predictions.png.webp)

第二个示例显示了如何结合[散点图(Scatter Plot)][散点图]使用 **支持向量机(SVM)**。以下工作流程在 *iris* 数据上训练 SVM 模型并输出支持向量，这些向量是在学习阶段用作支持向量的那些数据实例。我们可以在[散点图(Scatter Plot)][散点图]可视化中观察是哪些数据实例。请注意，为使工作流正常工作，必须设置小部件之间的链接，如下面的截图所示。


![](/assets/images/model/SVM-support-vectors.png.webp)

## 参考文献

[Introduction to SVM on StatSoft](http://www.statsoft.com/Textbook/Support-Vector-Machines).

{% include _links.md %}