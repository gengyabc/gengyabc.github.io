以一个简单的 [mnist 手写数字识别数据](https://share.weiyun.com/67OaQ5MO)为例, 工作流如图所示:

![](/assets/images/deeplearning/mnist_workflow.png.webp)

这里, 使用[卷积神经网络学习器] 设置卷积神经网络结构, [图片加载器]加载训练和测试数据, [图片加载器] **(1)** 加载想要预测的图片, [模型训练与测试]对模型训练并测试, 其结果可以通过[散点图]进行观察, 还可以在[卷积神经网络预测]进行预测.

### 卷积神经网络学习器设置

使用默认参数，点击“观察并输出模型”按钮，右侧主界面出现模型结构和参数。

![](/assets/images/deeplearning/cnnlearner_example.png.webp)

### 图片加载器设置

如果要训练模型, 注意选择 `需要训练`. 这里加载[mnist_sample](https://share.weiyun.com/67OaQ5MO)数据集（或者“mninst”数据集，但是数据集比较大，训练会花更多时间）。

![](/assets/images/deeplearning/imageloader.png.webp)


如果不需要训练, 载入的图片用来预测, 则选择 `只要预测`, 比如在[图片加载器] **(1)** 中采用此设置

![](/assets/images/deeplearning/imageloader_pre.png.webp)

### 模型训练与测试设置

打开“模型训练与测试”，保持默认设置，点击“开始训练”

![](/assets/images/deeplearning/train_test.png.webp)

### 神经网络预测

此小部件给出预测结果

![](/assets/images/deeplearning/pred.png.webp)