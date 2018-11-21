---
bilibili_id: 
youku_id: 
youtube_id: 
description: 
chapter: 1
title: Test data 语法
date: 2018-10-3

author: wang liyao
post-headings:
  - 文件和目录
  - 支持的文件格式
  - Test data 表格
  - 解析数据的规则
---


{% include assign-heading.html %}

安排测试用例的层次结构如下:
- 测试用例是在测试用例文件中创建的。
-  一个测试用例文件自动创建一个包含该文件中的测试用例的测试套件(suite)。
- 包含测试用例文件的目录形成一个更高级的测试套件。这样的测试套件目录有从测试用例文件中创建的套件作为它的子测试套件。
- 一个测试套件目录也可以包含其他的测试套件目录，这个层次结构可以像需要的那样深度嵌套。
- 测试套件目录可以有一个特殊的初始化文件。

除此之外，还有：
- 测试库包含最低级的关键字。
- Resource 文件是包含变量(variables) 和 高级别的用户keywords.
- 变量文件(Variable files) 比resource文件提供更加灵活的创建变量的方法.


{% include assign-heading.html %}

Robot Framework 测试数据是用表格式的格式来书写,使用超文本标记语言 (HTML),制表符分隔值(TSV),纯文本，或重新构造文本（reST）格式,
这些格式的详细信息，以及它们的主要优点和问题，将在后面的章节中解释。使用哪种格式取决于上下文，但是如果没有特殊需要，则推荐纯文本格式。


**纯文本**

纯文本格式很容易使用任何文本编辑器进行编辑，而且它们在版本控制中也很好地工作。由于这些好处，它已经成为了机器人框架中使用最多的数据格式。

在纯文本文件中，tabs 被自动转换为两个空格。这允许使用单个tabs作为分隔符，类似于TSV格式。然而，请注意，在纯文本格式中，多个tabs 被认为是单个分隔符，而在TSV格式中，每个tabs都是一个分隔符, 纯文本的example如下:

```
*** Settings ***
Library       OperatingSystem

*** Variables ***
${MESSAGE}    Hello, world!

*** Test Cases ***
My Test
    [Documentation]    Example test
    Log    ${MESSAGE}
    My Keyword    /tmp

Another Test
    Should Be Equal    ${MESSAGE}    Hello, world!

*** Keywords ***
My Keyword
    [Arguments]    ${path}
    Directory Should Exist    ${path}
```


{% include assign-heading.html %}

测试数据的结构是下面列出的四种类型的表。这些测试数据表由表的第一个单元格标识。被识别的表名是设置、变量、测试用例和关键字。匹配是不区分大小写的，并且还可以接受诸如设置和测试用例这样的奇异变体。

| Table        |  Used for                                                                                      |
| ------------ | -------------------------------------------------------------------------------------------    |
| Settings     | 1,Importing test libraries, resource files and variable files.2,为测试套件和测试用例定义metadata.|
| Variables    | 定义可以在测试数据的其他地方使用的变量                                                            |
| Test Cases   | 根据可用的keyword创建test cases                                                                 |
| Keywords     | 从已存在的低级别的keyword创建用户级别的keyword                                                    |




{% include assign-heading.html %}

**忽略数据**
当Robot Framework处理如下情景数据时他会忽略:

- 所有的表都不是在第一个单元中以一个公认的表名开始的。
- 除了第一个单元格之外的第一行的其他所有东西。
- 所有的空单元格，除非它们被转义。


当robot框架忽略一些数据时，这些数据在任何结果报告中都是不可用的，另外，大多数使用robot框架的工具也忽略了它们。要添加在robot框架输出中可见的信息，将其放置到测试用例或套件的文档或其他元数据中，或者用内置关键字日志或注释记录它。

**处理空格**
robot框架处理空白的方式与在HTML源代码中处理的方式相同：
- 换行符、回车符和制表符被转换成空格
- 所有单元中的前导和尾随空格都被忽略了。
- 多个连续空间被折叠成一个单独的空间。