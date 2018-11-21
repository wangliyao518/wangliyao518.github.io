---
bilibili_id: 
youku_id: XMzg1ODMwMzA1Mg
youtube_id: 
description: 
chapter: 1
title: 安装
date: 2018-10-3

author: wang liyao
post-headings:
  - Mac 安装
  - Windows 安装
  - Linux 安装
  - 检查安装是否成功
---




{% include assign-heading.html %}

Mac用户安装 python会比较方便,直接到[官网](www.python.org)下载安装包，
下载自己需要的版本，默认路径安装即可。之后的某节会讲到如何给Mac中的python安装其他模块，
比如比较常用的`numpy` 或者`matplotlib`.



{% include assign-heading.html %}

请到[官网](www.python.org)下载需要的版本的安装包，
下载所需(注意自己的系统是32位还是64位)，安装路径最好选择默认, 不然对于新手容易出现各种问题。

Windows 安装附加要点:
设置环境变量:
1.找到安装路径, 默认 `C:\Users\**你的用户名**\AppData\Local\Programs\Python\Python35-32` 粘贴路径
2.我的电脑 - 属性 - 高级 - 环境变量 - 系统变量中的PATH为（复制路径）:
`C:\Users\**你的用户名**\AppData\Local\Programs\Python\Python35-32;`

pip3 设置环境变量: 
`C:\Users\**你的用户名**\AppData\Local\Programs\Python\Python35-32\Scripts;`

{% include assign-heading.html %}

Linux 安装附加要点:
1.首先，官网下载python3的所需版本。
想下载到那个文件夹下就先进入到那个文件夹下执行
cd /home/download; 
wget https://www.python.org/ftp/python/3.6.0/Python-3.6.0.tgz


2.压缩解压, 执行命令:tar -xvf Python-3.6.0.tgz

3.创建安装路径: mkdir /usr/local/python3

4.编译:./configure --prefix=/usr/local/python3

5.安装: make; make install

6.创建新版本的连接:mv /usr/bin/python /usr/bin/python_bak; ln -s /usr/local/python3/bin/python3 /usr/bin/python

{% include assign-heading.html %}

打开`idle`, `print(1)` 如果系统输出`1`,则表明安装成功.

```python
>>> print(1)
1
>>>
```

