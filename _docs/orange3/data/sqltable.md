---
title: "SQL表(SQL Table)"
---

从数据库读取数据




## 输出

- 数据: 数据库的数据集


## 功能
**SQL**小部件访问存储在SQL数据库中的数据。它可以连接到 `PostgreSQL`（需要[psycopg2](http://initd.org/psycopg/)模块）或 [SQL Server](https://www.microsoft.com/zh-cn/sql-server/)（ 需要[pymssql](http://pymssql.org/en/stable/)模块）。

为了处理大型数据库，`Orange` 尝试在数据库本身中执行部分计算，而无需下载数据。 这仅适用于`PostgreSQL`数据库，并且需要在服务器上安装 `quantile` 和tsm_system_time [extensions](https://github.com/biolab/orange3/wiki/Installation-of-SQL-extensions)。 如果未安装这些扩展，则数据将在本地下载。

## 界面

![](/assets/images/data/SQLTable-stamped.png.webp)

1.数据库类型（可以是 `PostgreSQL` 或 `MSSQL`）。
2.主机名。
3.数据库名称。
4.用户名。
5.密码。
6.按蓝色按钮连接到数据库。 然后在下拉列表中选择表。
7. **自动发现分类变量**会将具有少于20个不同值的 `INT` 和` CHAR` 列转换为分类变量（在大表上发现所有不同值可能很慢）。 如果未选择，则 `INT` 将被视为数字，而 `CHAR` 将被视为文本。 **下载到本地存储器**将所选表下载到本地计算机。

## 安装指引

### PostgreSQL

Install the backend.

    pip install psycopg2

Alternatively, you can follow [these instructions](https://blog.biolab.si/2018/02/16/how-to-enable-sql-widget-in-orange/) for installing the backend.

If the installation of `psycopg2` fails, follow to instructions in the error message you get (it explains how to solve the error) or install an already compiled version of `psycopg2-binary` package:

    pip install psycopg2-binary

Note: `psycopg2-binary` comes with own versions of a few C libraries, among which libpq and libssl, which will be used regardless of other libraries available on the client: upgrading the system libraries will not upgrade the libraries used by psycopg2. Please build psycopg2 from source if you want to maintain binary upgradeability.

[Install the extensions](https://github.com/biolab/orange3/wiki/Installation-of-SQL-extensions). [optional]

### MSSQL

Install the backend.

    pip install pymssql

If you are encountering issues, follow [these instructions](https://github.com/biolab/orange3/wiki/Installation-of-SQL-extensions#mssql).

## 例子

这是一个有关如何使用此小部件的简单示例。 将小部件放在画布上，输入数据库凭据并连接到数据库。 然后选择您要分析的表。

将此小部件 **连接到 [数据表(Data Table)][数据表] 小部件以检查输出。 如果该表已填充，则您的数据已正确传输。 现在，您可以以与 [文件(File)][文件] 小部件相同的方式** 使用此小部件。

![](/assets/images/data/SQLTable-Example.png.webp)

{% include _links.md %}