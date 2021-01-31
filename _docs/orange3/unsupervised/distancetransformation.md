---
title:  距离变换(Distance Transformation)
---

转换数据集中的距离。






## 输入
- 距离：距离矩阵


## 输出
- 距离：变换后的距离矩阵


## 功能
**距离变换(Distance Transformation)** 小部件用于距离矩阵的归一化和反转。为了使所有变量相互成比例，应该对数据进行归一化。



## 界面
![](/assets/images/unsupervised/DistanceTransformation-stamped.png.webp)

1. 选择[归一化](https://en.wikipedia.org/wiki/Normalization_\(statistics\))的类型：
    - `无归一化`
    - `至间隔[0，1]`
    - `至间隔[-1，1]`
   - [Sigmoid function](https://en.wikipedia.org/wiki/Sigmoid_function): 1/(1+exp(-X))
2. 选择翻转类型:
   - `无`
   - `-X`
   - `1 - X`
   - `max(X) - X`
   - `1/X`
3. 生成报告
4. 勾选 **自动应用** 以自动将更改提交到其他窗口小部件。 或者，按 **应用**。

## 示例
在下面的截图中，您可以看到变换如何影响距离矩阵。 我们加载了 *Iris* 数据集，并借助[距离(Distances)][距离] 小部件计算了行之间的距离。为了演示**距离变换(Distance Transformation)** 如何影响[距离矩阵(Distance Matrix)][距离矩阵]，我们在下面创建了工作流程，并将转换后的距离矩阵与“原始”矩阵进行了比较。


![](/assets/images/unsupervised/DistanceTransformation-Example.png.webp)


{% include _links.md %}
