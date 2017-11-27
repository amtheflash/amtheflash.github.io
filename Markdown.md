---
title: Markdown的扩展格式
tags: [markdown分类,md]
date: 2017-11-27 14:03:44
categories: Markdown
toc: true
---
## 说明
----------
`Markdown` 是为网络书写者而生的方便`text-to-HTML`工具，它允许人们用一种易读易写的纯文本格式进行书写，然后将其转化成`XHTML`或`HTML`

## 扩展格式
----------
常用扩展Markdown格式有:

`GFM` `PHP Markdown Extra` `MultiMarkdown` `Pandoc Markdown`等。
### GFM
----------
这种衍生`Markdown`叫做**Github Flavored Markdown**，简称 **GFM** 
> 详细说明：https://help.github.com/categories/writing-on-github/

#### 与原生Markdown的主要不同：
----------
- 围栏式（`Fenced`）代码块：在代码的上下增加3个反引号```，可选择性定义代码语种，并支持代码高亮。
- 列表嵌套方法：改为每次嵌套缩进两个空格。
- 支持任务列表：在每个列表项目加入[ ]，完成任务用 [x]，如：- [x] 任务说明。
- 支持简单表格
- 支持emoji表情
- 删除线：~~无空格包裹。
### PHP Markdown Extra
----------
 Markdown Extra是PHP Markdown的一个扩展，实现了当前Markdown语法所不具备的一些功能。 Markdown Extra在PHP Markdown Lib中作为单独的解析器类提供

> 详细的语法说明：https://michelf.ca/projects/php-markdown/extra/ 

#### 与原生Markdown的主要不同：
----------

- 内嵌html：块标签可以缩进不超过3个空格，且可以在块标签中选择性使用markdown语法（方法略）。
- 可以为区块元素设置id和class属性，实现文章内部跳转，方法略。
- 区块代码：与GFM相似，可以使用栅栏方式，在代码上下行用3个或以上波浪号~或反引号`包裹，亦支持代码高亮。
- 表格：同GFM
- 支持定义列表：方法略
- 支持脚注：[^1]，在新行[^1]: 脚注内容  ***注意***：脚注名字必须唯一
- 支持缩略语：方法略
- 强调：两字词中间的下划线不会被解释成强调

### MultiMarkdown
----------
原生markdown文档只能从纯文本转换HTML。而MultiMarkdown则是扩大了原生markdown的转换范围，让其可以方便的转换成`HTML/XHTML` `LaTeX (which can be processed into a PDF)` `OpenDocument Text document` `OPML` 

> 详细的语法说明见：http://fletcherpenney.net 
这是语法快速查询表：https://rawgit.com/fletcher/human-markdown-reference/master/index.html

#### 与原生Markdown的主要不同：
 - 支持元数据：标题、作者、日期等信息，兼容部分YAML。
 - 支持交叉引用。
 - 支持添加链接和图片的属性。
 - 图片可以作为区块元素：如果一个图片语言独立成段，会被自动解释为区块元素，图片下会添加一行图片说明。
 - 支持部分复杂表格：兼容PHP Markdown Extra的表格，同时可以——多行表头，单元格横向合并，表格分区，表格下行表格说明等。
 - 支持脚注：同PHP Markdown Extra中的脚注。
 - 支持参考文献（Citations）
 - 支持定义列表：同PHP Markdown Extra。
 - 支持缩略语（Abbreviations）：同PHP Markdown Extra。
 - 支持栅栏式区块代码：上下行3到5个反引号包裹代码，可定义语法种类，选择性语法高亮。 
 - 注意：首尾行的反引号数量要一致。
 - 支持MathJax公式（区块与行内）：区块公式在新行用\\[和\\]包裹，或首尾用两个dollar$$包裹。行内公式用\\(和\\)包裹，或首尾各用一个dollar$包裹。
 - 支持上标与下标：上标为单个字符，前面加^，为多个字符，用^包裹。下标为单个字符，前面加~，为多个字符，用~包裹。
 - 支持术语表
 - 支持修订功能（CriticMarkup）：可以显示修订痕迹
	- 删除：{--删除的文本 --}
	- 添加：{++新增的文本 ++}
	- 替换：{~~删除的文本~>新增文本~~}
	- 高亮：{==高亮的文本==}
	- 备注：{>>备注文本<<}
	
- 内嵌HTML，可在块级HTML中选择性地添加MultiMarkdown语法。
- 支持内嵌其他文件，txt、tet、fodt、html等
- 换行方式改为行末使用\换行。（原生Markdown使用2个空格换行）
- 支持目录：{{TOC}}添加目录
### Pandoc's Markdown
----------
Pandoc本身是一个多格式文档的转换工具，所以Pandoc Markdown与MultiMarkdown的设计目的相似，使Markdown可以转换成更多的不同格式，因为Pandoc支持的格式很多，这也就使的Pandoc's Markdown非常的丰富，比如表格就有4种不同的书写方法。

> 详细的语法说明见：http://pandoc.org/MANUAL.html#pandocs-markdown 
翻译的中文版：http://pages.tzengyuxio.me/pandoc/


#### 与原生Markdown的主要不同：

- 强制换行支持两种方式：行尾两个空格换行，反斜杆换行。
- Atx式标题之前一定要预留空行。标题行尾可加标题识别符。
- 区块引用之前一定要预留空行。
- 围栏式区块代码可以用3个以上波浪线或反引号组成的行包裹代码。之前必须留空行。
- 支持行区块
- 不同形式的列表会生成不同的列表
- 支持连续编号的范例清单，范例项目应用与整个文档，不局限与单一清单
- 支持定义列
- 支持简单表格、多行表格、格框表格和管线表格四种表格样式
- 支持文件标题区块（类似元数据）
- 支持删除线
- 支持上标、下标
- 支持数字公式
- 支持内嵌TeX

### CommonMark
由于创始人自2004年Markdown诞生之后就没有更新过Markdown语法，众多的遗留问题没有得到解决，加上扩展语法的自由发展和Markdown编辑器的涌现，导致了很严重的方言和兼容性问题。因此有人希望对Markdown语法进行规整和统一，建立一套Markdown的语法规范，而CommonMark正是这样产物。CommonMark与一般的衍生语法不同，它的目的不是扩展Markdown的功能，而是解决原生markdown的遗留问题和方言问题，规范Markdown的书写，成为Markdown的标准。可惜此举得到Markdown创始人John Gruber的强力反对，所以至今CommonMark并没有得到广泛的认可。但是其实就CommonMark本身而言，它规范了Markdown的各项语法，有许多可取之处。CommonMark的语法说明是所有markdown语法说明中最长最详细的，优先问题、缩进问题、空行问题、嵌套问题等等容易出现语法冲突的地方都作了非常详细的说明

> 详细的语法说明：http://spec.commonmark.org/

#### 与原生Markdown的主要不同：

- 定义了优先级别：区块语法的优先级别大于行内语法。
- 支持围栏式区块代码
- 支持1）作为有序列表的项目标记
- 支持 \作为换行符。
- 列表嵌套采用行首内容对齐，而非4个空格
- Setext式标题支持多行

> 更多Markdown相关知识请访问https://sspai.com/post/37264