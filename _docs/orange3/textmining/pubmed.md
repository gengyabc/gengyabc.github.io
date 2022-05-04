---
title: Pubmed
---

## 输入

- 无

## 输出

- 语料库:  来自PubMed在线服务的文件集.





## 功能
[PubMed](http://www.ncbi.nlm.nih.gov/pubmed) 包括来自 MEDLINE，生命科学期刊和在线书籍的生物医学文献的超过2600万次引用。该小部件允许您查询和检索这些条目。您可以使用常规搜索或构造高级查询。

![](/assets/images/text/Pubmed-stamped.webp)

1. Enter a valid e-mail to retrieve queries.
2. *Regular search*:
   - *Author*: queries entries from a specific author. Leave empty to query by all authors.
   - *From*: define the time frame of publication.
   - *Query*: enter the query.
   *Advanced search*: enables you to construct complex queries. See [PubMed's website](https://www.ncbi.nlm.nih.gov/pubmed/advanced) to learn how to construct such queries. You can also copy-paste constructed queries from the website.
3. *Find records* finds available data from PubMed matching the query. Number of records found will be displayed above the button.
4. Define the output. All checked features will be on the output of the widget.
5. Set the number of record you wish to retrieve. Press *Retrieve records* to get results of your query on the output. Below the button is an information on the number of records on the output.

Example
-------

**PubMed** can be used just like any other data widget. In this example we've queried the database for records on orchids. We retrieved 1000 records and kept only 'abstract' in our meta features to limit the construction of tokens only to this feature.

![](/assets/images/text/Pubmed-example.webp)

We used [文本预处理]to remove stopword and words shorter than 3 characters (regexp `\b\w{1,2}\b`). This will perhaps get rid of some important words denoting chemicals, so we need to be careful with what we filter out. For the sake of quick inspection we only retained longer words, which are displayed by frequency in [词云].

{% include _links.md %}