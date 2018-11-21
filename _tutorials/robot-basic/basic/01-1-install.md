---
bilibili_id: 
youku_id: 
youtube_id: 
description: 
chapter: 1
title: 安装
date: 2018-10-3

author: wang liyao
post-headings:
  - linxu 安装
  - Windows 安装
  - 检查安装是否成功
---




{% include assign-heading.html %}

打开[官网](http://robotframework.org/)
在官网的introduction部分有如下介绍, 点开PYPI链接或者GiHub链接地址, 有详细的安装步骤
Robot Framework project is hosted on [GitHub](https://github.com/robotframework/robotframework) where you can find further documentation, source code, and issue tracker. Downloads are hosted at [PyPI](https://pypi.org/project/robotframework/#installation). The framework has a rich ecosystem around it consisting of various generic test libraries and tools that are developed as separate projects.



{% include assign-heading.html %}

如果已经安装了python和pip工具, 直接通过pip安装
- pip install robotframework

如果通过github下载源码下来安装.
首先需要解压缩,然后启动shell 或者 cmd窗口, 在setup.py目录执行
- python setup.py install


{% include assign-heading.html %}
在cmd(windows环境)或是shell(linux环境)执行如下命令:
- pybot --version
安装成功会有如下类似提示:
Robot Framework 3.0.4 (Python 2.7.13 on win32)