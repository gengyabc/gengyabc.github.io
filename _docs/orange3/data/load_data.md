---
title: "加载数据"
---

橙现智能拥有自己的数据格式，也可以处理Excel，逗号或制表符分隔的数据文件。





输入数据集通常是一个表，行中有数据实例（样本），列中有数据属性。属性可以具有不同的类型（数字，分类，日期时间和文本），并具有分配的角色（特征，元属性和类）。可以在数据表表头设置数据类型和角色，也可以在[文件(File)][文件]小部件中进行更改，数据角色也可以通过[选择列(Select Columns)][选择列]小组件进行修改。


## 简介
- 橙现智能可以导入任何用逗号或制表符分隔的数据文件，Excel文件或网址。使用[文件(File)][文件]小部件来加载数据，并在需要时定义类和元属性。
- 为了指定数据属性，列标题中的名称可以写作 "类型#标签名"形式。c 代表类别， m 代表元属性，i 代表忽略列，C，D，S 分别代表连续，离散和字符串属性类型。例如：C#mph，mS#name，i#dummy。
- 橙现智能的原始格式是制表符分隔的数据文件，该文件含三行标题。 第一行包含属性名称，第二行包含属性类型（continuous(连续)，discrete(离散)或string(字符串)），第三行可选（class，meta或time）。


## Excel 数据

![](/assets/images/data/spreadsheet1.png.webp)


该文件包含一个标题行，八个数据实例（行）和七个数据属性（列）。表中的空白单元格表示缺少数据条目。行代表基因；第一列提供了它们的功能（类），第二列提供了它们的名称。其余列存储表征每个基因的测量值。有了这些数据，可以说，我们可以开发出一个分类器，通过它的特征测量来预测基因功能。

让我们从一个简单的工作流程开始，该工作流程读取数据并将其显示在表中：

![](/assets/images/data/file-data-table-workflow.png.webp)

要加载数据，请打开 [文件(File)][文件] 小部件（双击小部件的图标），单击文件浏览器图标("...") ，然后在磁盘上找到下载的文件（[sample.xlsx](../data/sample.xlsx)）：

![](/assets/images/data/File.png.webp)


## 文件小部件：设置属性类型和角色

[文件(File)][文件] 的数据发送到数据表。双击 [数据表(Data Table)][数据表] 以查看其内容：
 
![](/assets/images/data/table-widget.png.webp)

橙现智能正确地推断具有基因名称的列为元信息，该列在 [数据表(Data Table)][数据表] 中以浅棕色阴影显示。但是 橙现智能没有正确推断出 *function*（第一个非元属性列）是类别数据。要在橙现智能中纠正此问题，我们可以在 [文件(File)][文件] 小部件的列显示中调整属性角色（如下所示）。双击功能行中的功能标签，然后选择目标。这会将功能属性设置为我们的目标（类）变量。

![](/assets/images/data/File-set-feature-kind.png.webp)

您还可以将属性类型从从字符串更改为日期时间，依此类推。日期时间仅接受[ISO 8601](https://en.wikipedia.org/wiki/ISO_8601)格式的值，例如2016-01-01 16:16:01。如果属性具有多个不同的值，橙现智能也将假定该属性是数字的，否则它将被视为分类数据。所有其他类型均视为字符串，因此会自动归类为元属性。
属性角色和类型的更改应通过单击 **应用** 按钮来确认。

### 选择列：设置属性角色
设置数据角色的另一种方法是将数据发送到[选择列(Select Columns)][选择列]小部件：

打开 **“选择列(Select Columns)”** 将显示橙现智能的属性分类。我们希望所有的连续属性成为数据特征，`function` 作为目标变量，而 `gene` 被视为元属性。我们可以通过在 “选择列(Select Columns)” 中拖动属性名称来设置这些信息：

![](/assets/images/data/select-columns-start.png.webp)

要正确地重新分配属性类型，`function` 拖动到“目标”，`gene` 拖动到元属性。如下所示：

![](/assets/images/data/select-columns-reassigned.png.webp)

应通过单击“应用”按钮来确认属性类型的更改。来自此小部件的数据传送到[数据表(Data Table)][数据表]中，该表现在按照我们期望的方式呈现数据：

![](/assets/images/data/data-table-with-class1.png.webp)

我们还可以通过其他方式为此数据集定义域。比如我们可以使数据集进行回归，并使用 `heat 0` 作为连续目标变量，保留`function`和`gene`作为元变量，并从数据集中删除`heat 10`和`heat 20`：

![](/assets/images/data/data-table-regression1.png.webp)

通过如上所述设置属性，在[数据表(Data Table)][数据表]小部件中呈现数据为：

![](/assets/images/data/data-table-regression.png.webp)

## 头与属性类型信息

再次考虑刚才的 *sample.xlsx* 数据集。这次，我们将使用定义属性类型（连续，离散，时间，字符串）和角色（类或元属性）的前缀来扩展属性名称。前缀与属性名称以 **“＃”** 分隔。属性角色的前缀为：
- c：类属性
- m：元属性
- i：忽略属性
- w：实例权重
和类型：
- C：连续
- D：离散
- T：时间
- S：字符串
这是带有扩展属性名称的表在Excel（[sample-head.xlsx](../data/sample-head.xlsx)）中的样子：

![](/assets/images/data/spreadsheet-simple-head1.png.webp)

我们可以再次使用“文件（File）”小部件来加载此数据集，然后将其呈现在“数据表（Data Table）"中：

![](/assets/images/data/select-cols-simplified-header.png.webp)

注意，我们忽略的属性（属性名称中的标签“ i”）不存在于数据集中。

## 三行标题格式
橙现智能的原生数据格式是带有三行表头的制表符分隔的文本文件。第一行列出属性名称，第二行定义它们的类型：continuous, discrete, time 和 string（连续，离散，时间和字符串），或缩写为c，d，t和s，第三行定义了可选角色（类，元，权重或忽视）。比如:

![](/assets/images/data/excel-with-tab1.png.webp)

 
## Google表格中的数据

橙现智能可以从Google表格中读取数据，只要它符合我们上面介绍的数据表示规则即可。在Google表格中，复制可共享链接（“共享”按钮，然后获取“可共享链接”）并将其粘贴到“文件”小部件的“ 数据文件/ URL”框中。尝试一下，可以使用以下这样的链接：http : //bit.ly/1J12Tdp，以及我们在“ 文件”小部件中输入它的方式：


## 来自LibreOffice的数据
如果你使用的是LibreOffice，只需将文件保存为Excel（.xlsx）格式（可从“ 另存为类型”下的下拉菜单中获得）。

## DateTime格式
为避免歧义，橙现智能支持以ISO 8601格式之一格式的日期和/或时间。例如，以下值均有效：
2016
2016-12-27
2016-12-27 14:20:51
16:20


{% include _links.md %}