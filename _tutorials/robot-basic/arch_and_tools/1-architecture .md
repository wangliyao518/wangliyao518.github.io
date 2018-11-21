---
bilibili_id: 
youku_id: 
youtube_id: 
description: 
chapter: 1
title: architecture 
date: 2018-10-5

author: wang liyao
post-headings:
  - Robot Framework architecture
  - robot case和报告截图示例
---




{% include assign-heading.html %}

robot框架是一个通用的、应用和技术独立的框架。它有一个高度模块化的体系结构，如下图所示。

![Robot Framework architecture](http://robotframework.org/robotframework/latest/images/architecture.png)

测试数据采用简单、易于编辑的表格格式。当启动robot框架时，它处理测试数据，执行测试用例并生成测试日志和测试报告。核心框架不知道测试中的目标，并且与它的交互是由测试库来处理的。库既可以直接使用应用程序接口，也可以使用低级测试工具作为驱动程序。

{% include assign-heading.html %}

下面的截图显示了测试数据的示例，并创建了报表和日志

test case files
![test case](http://robotframework.org/robotframework/latest/images/testdata_screenshots.png)

Reports and logs
![report](http://robotframework.org/robotframework/latest/images/screenshots.png)