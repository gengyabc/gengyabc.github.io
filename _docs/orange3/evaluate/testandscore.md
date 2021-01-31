---
title: 测试与评分(Test and Score)
---
测试数据的学习算法






## 输入
- 数据：输入数据集
- 测试数据：单独的用于测试的数据
- 学习器：学习算法


## 输出
- 评价结果：测试分类算法的结果

## 功能

此小部件测试学习算法。可以使用不同的采样方案，包括使用单独的测试数据。该小部件有两个功能: 首先，是不同分类器性能指标的表格，例如[分类准确率](https://en.wikipedia.org/wiki/Accuracy_and_precision)和[曲线下面积](https://en.wikipedia.org/wiki/Receiver_operating_characteristic#Area_under_the_curve)。其次，它输出评估结果，其他小部件可以使用评估结果来分析分类器的性能，例如[ROC 分析] 或者 [混淆矩阵]。

*学习器* 输入具有一个不常见的属性：它可以连接到多个控件上，以相同的步骤测试多个学习器。


## 界面
![](/assets/images/evaluate/TestAndScore-stamped.png.webp)

1. 小部件支持各种采样方法。
   - [交叉验证](https://en.wikipedia.org/wiki/Cross-validation_\(statistics\)) 将数据拆分为给定的折叠倍数(通常为5或10)。通过每次保留一个折叠的数据来测试；该模型从其他折叠中训练，从保留的折叠中对数据进行分类测试。对于所有折叠都重复此步骤。
   - `按特征交叉验证`执行交叉验证，但折叠由元特征中选择的分类特征定义。
   - `随机抽样`，以给定比例(例如70:30)将数据随机分为训练和测试集；整个过程重复指定的次数。
   - `留一法`与 **交叉验证** 类似，但是它一次保留一个实例，从所有其他数据中导出模型，然后对保留的一个实例进行分类。这种方法显然非常稳定，可靠...而且非常慢。
   - `测试训练数据`使用整个数据集进行训练，然后进行测试。这种方法实际上总是给出错误的结果。
   - `测试测试数据`：上述方法仅使用 `数据` 信号中的数据。要输入带有测试数据的另一个数据集(例如，来自另一个文件或在另一个小部件中选择的某些数据)，我们在通信通道中选择 `测试数据` 信号，然后选择`测试测试数据`。
   
2. 对于分类，可以在小部件底部选择 `目标类别`。 当`目标类别`为(所有类别的平均值)时，方法返回的分数是所有类的加权平均值。例如，在分类器具有 3 个类别的情况下，将类别 1 作为目标类别，类别 2 作为目标类别，将类别 3 作为目标类别计算得分。根据类别大小对这些分数进行加权平均，以获取最终分数。
3. 小部件将计算许多性能统计信息。默认情况下显示一部分。要查看其他部分，请右键单击表头，然后选择所需的统计信息。

   - 分类
  ![](/assets/images/evaluate/TestAndScore-Classification.png.webp)

     - [ROC下的面积](http://gim.unmc.edu/dxtests/roc3.htm)是接收者操作曲线下的面积。
     - [分类准确率](https://en.wikipedia.org/wiki/Accuracy_and_precision)是正确分类的样本所占的比例。
     - [F-1](https://en.wikipedia.org/wiki/F1_score)是精确度和召回率的加权谐波平均值(请参见下文)。
     - [精度](https://en.wikipedia.org/wiki/Precision_and_recall)是分类为阳性的实例中真阳性的比例。
     - [召回](https://en.wikipedia.org/wiki/Precision_and_recall)是数据中所有阳性中真阳性例的比例。
     - [特异度](https://en.wikipedia.org/wiki/Sensitivity_and_specificity)是在所有阴性实例中真阴性的比例。
     - [LogLoss](https://en.wikipedia.org/wiki/Cross_entropy)或交叉熵损失会根据预测值与实际标签的差异来考虑预测的不确定性。
     - `训练时间`: 用于训练模型的累积时间(以秒为单位)。
     - `测试时间`: 用于测试模型的累积时间(以秒为单位)。


   - 回归
  ![](/assets/images/evaluate/TestAndScore-Regression.png.webp)

       - [MSE](https://en.wikipedia.org/wiki/Mean_squared_error)测量误差或误差平方的平均值(估计量与估计量之间的差)。
       - [RMSE](https://zh.wikipedia.org/wiki/Root_mean_square)是一组数字的平方的算术平均值的平方根(度量估计量对数据的拟合的不完美程度)
       - [MAE](<https://en.wikipedia.org/wiki/Mean_absolute_error>)用于衡量预测或预测与最终结果的接近程度。
       - [R2](<https://en.wikipedia.org/wiki/Coefficient_of_determination>)解释为因变量中从自变量可预测的方差比例。
       - [CVRMSE](https://en.wikipedia.org/wiki/Root-mean-square_deviation)是通过实际值的平均值归一化的RMSE。
       - `训练时间`: 用于训练模型的累积时间(以秒为单位)。
       - `测试时间`: 用于测试模型的累积时间(以秒为单位)。

4. 选择分数以成对比较模型和实际等效区域（ROPE），此区域内差异可忽略不计。
5. 使用所选分数成对比较模型（仅适用于交叉验证）。表中的数字给出了与行相对应的模型优于与列相对应的模型的可能性。 如果启用了可忽略的差异，则下面较小的数字表示该对之间的差异可忽略的可能性。 该测试基于[t检验的贝叶斯解释](https://link.springer.com/article/10.1007/s10994-015-5486-z) ([简单解释好](https://baycomp.readthedocs.io/en/latest/introduction.html)).。
6. 获取帮助并生成报告。 


## 示例
在此小部件的典型用法中，我们为它提供了一个数据集和一些学习算法，我们在 **测试与评分(Test and Score)** 小部件内的表中以及[ROC 分析]中观察它们的性能。数据通常在测试之前进行预处理； 在这种情况下，我们对 *Titanic* 数据集使用[选择列(Select Columns)][选择列]进行了一些手动特征选择，我们只想知道幸存者的性别和状态，并忽略了年龄。


在下面的表格中，我们进行模型的成对比较。我们选择了基于 `ROC去显现面积` 进行比较。 表中的数字给出了与行相对应的模型优于与列相对应的模型的可能性。 例如，我们可以看到树优于 SVM 的几率几乎是 1，树优于朴素贝叶斯的几率是 0.001。表中的数字越小，基于可忽略的阈值0.1，该对之间的差异就更可能忽略不计。


![](/assets/images/evaluate/TestAndScore-Example.png.webp)

[混淆矩阵(Confusion Matrix)][混淆矩阵] 小部件的文档中提供了使用此小部件的另一个示例。

{% include _links.md %}