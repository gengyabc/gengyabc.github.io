---
title: 连续化(Continuize)
---

将离散变量（属性）转换为数字（连续）变量。




## 输入
- 数据：输入数据集

## 输出
- 数据：转换后的数据集

## 功能
**连续化(Continuize)** 小部件从输入接收数据集，并输出离散变量（包括二进制变量）被连续变量替换的数据集。

## 界面

![](/assets/images/data/Continuize-stamped.png.webp)

1. 定义对非二进制分类变量的处理。

   本节中的示例将假定我们具有离散的属性状态，该属性状态的值分别为 `low`, `middle` 和 `high`。 其转换的选项有：
   - `以第一个值作为基数`：一个 N 值的分类变量将转换为 N-1个数字变量（即一列分类变量变为了 N-1 列数字变量）。`基数`是列表中的第一个值。 默认情况下，这些值按字母顺序排序； 它们的顺序可以在 [编辑特征(Edit Domain)][编辑特征] 中更改。

     > 在上述情况下，三值变量 `status` 被转换为两个数字变量，即 `status = middle` 的值为 0 或 1，表示特定示例中原始变量的值是否为 `middle`，类似地也有`status = high`。

   - `最常见值作为基数`：与上述类似，不同之处在于最常见的值被用作基数。 因此，如果在上面的示例中，最常见的值是 `middle`，则将 `middle` 视为基数，并且两个新构造的变量分别为 `status=  low` 和 `status = high`。

   - `每个值一个属性`：此选项为原始变量的每个值构造一个数字变量。在上述情况下，我们将获得变量`status = low`，`status = middle` 和 `status = high`。

   - `忽略多值属性`：从数据中删除非二元分类变量。

   - `按有序数据处`：将变量转换为枚举原始值的数字变量。在上述情况下，新变量的值将为 0(low），1（middle）和 2（high）。再次注意，可以在 [编辑特征(Edit Domain)][编辑特征] 中设置值的顺序。 

   - `除以取值数目`：除了数值标准化为 0-1 之间，与上述相同。 在我们的示例中，新变量的值为0、0.5和 1。
2. 定义连续属性的处理。 
3. 定义对类属性（结果，目标）的处理。 除了保持原样之外，可用选项反映了多值属性的选项，除了将结果分成多个结果变量的选项。
4. 此选项定义新变量的范围。 在上面的文本中，我们假设范围是 0 到 1。
5. 生成报告。
6. 如果勾选了“自动应用”，则会自动提交更改。 否则，每次更改后都必须按“应用”。

## 示例
首先，让我们看看 **连续化(Continuize)** 小部件的输出是什么。 我们将 *Heart disease* 数据集输入[数据表(Data Table)][数据表]。然后，我们连续化离散值并在另一个[数据表(Data Table)][数据表]中观察它

![](/assets/images/data/Continuize-Example1.png.webp)

在第二个示例中，我们展示了此小部件的典型用法 -- 为了正确绘制数据的线性投影，需要将离散属性转换为连续的属性，这就是为什么我们在绘制数据之前将数据通过 **连续化(Continuize)** 小部件。 `chest pain` 属性最初具有四个值，并被转换为三个连续属性。 `gender` 也发生了类似的情况，该属性被转换为单一属性 `gender=female`。

![](/assets/images/data/Continuize-Example2.png.webp)

{% include _links.md %}