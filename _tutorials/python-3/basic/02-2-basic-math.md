---
bilibili_id: 
youku_id: XMzg1ODMwMzA1Mg
youtube_id:
description: 
chapter: 2
title: 基础数学运算
date: 2018-10-3

author: wang liyao
post-headings:
  - 基本的加减乘除
  - ^ 与 **
  - 取余数 %
  - 取整除
  - 复数运算
---




{% include assign-heading.html %}

`python`可以直接运算数字，也可以加`print` 打印运算结果.

```python
>>> 1 + 1
2
>>> 2 - 1
1
>>> 2 * 3
6
>>> 4/3
1.3333333333333333
```

{% include assign-heading.html %}

`python`当中`^`符号，区别于`Matlab`，在`python`中，`^`用两个`**`表示，如3的平方为`3**2` , `**3`表示立方，`**4`表示4次方，依次类推

```python
>>> 4**2   # **2 表示2次方
""""
16
""""
>>> 3**3   #  **3 表示3次方
""""
27
""""
>>> 3**4   # 表示3的4次方 
""""
81
""""
>>> 4**0.5   # 表示4 开平方 
""""
2.0
""""
>>> pow(4, 2) # 表示4的2次方
""""
16
""""
```

{% include google-in-article-ads.html %}

{% include assign-heading.html %}

余数符号为`“%”`,见代码.

```python
>>> 8%3
"""
2
"""
```


{% include google-in-article-ads.html %}

{% include assign-heading.html %}

取整除 - 返回商的整数部分（向下取整）符号为`“//”`,见代码.

```python
>>> 9//2
"""
4
"""
>>> 9.0//2.0
"""
4.0
"""
```

{% include google-in-article-ads.html %}

{% include assign-heading.html %}

+ - * / 自然也支持复数运算, 见代码.

```python
>>> a = 1 + 2j
>>> b = 2 + 3j
>>> a + b
(3+5j)
>>> a * b
(-4+7j)
>>> b - a
(1+1j)
>>> b / a
(1.6-0.2j)
```
