---
bilibili_id: 
youku_id: XMzg1ODMwMzA1Mg
youtube_id:
description: 
chapter: 2
title: 打印(print)功能
date: 2018-10-3

author: wang liyao
post-headings:
  - print 字符串
  - print 字符串叠加
  - 简单运算
  - pprint模块 提供了打印出任何Python数据结构类和方法。
---






{% include assign-heading.html %}

`python` 中 `print` 字符串 要加`''`或者`""`

```python
>>> print 'hello world in python 2'
'''
hello world in python 2
'''
>>> print("hello world in python 3")
'''
hello world in python 3
'''
```

{% include assign-heading.html %}

可以使用 `+` 将两个字符串链接起来, 也可以像c语言一样,使用%s, 还克用format, 如下例子

```python
>>> print('hello' + 'china')
"""
hello china
"""
>>> print("hello %s" %"chengdu")
"""
hello chengdu
"""
>>> print("hello {}".format("hangzhou"))
"""
hello hangzhou
"""
```

{% include google-in-article-ads.html %}

{% include assign-heading.html %}

可以直接`print` 加法`+`,减法`-`,乘法`*`,除法`/`.  注意：字符串不可以直接和数字相加，否则出现错误。

```python
>>> print(1+1)
"""
2
"""
>>> print(2-1)
"""
1
"""
>>> print(2*3)
"""
6
"""
>>> print(12/4)
"""
3.0
"""
>>> print('debian'+ 8) #字符串不可以直接和数字相加
"""
Traceback (most recent call last):
  File "<pyshell#10>", line 1, in <module>
    print('debian' + 8)
TypeError: Can't convert 'int' object to str implicitly
"""
```

`int()` 和 `float()`；当`int()`一个浮点型数时，`int`会保留整数部分,比如 `int(1.6)`,会输出`1`,而不是四舍五入。

```python
>>> print(int('1') + 2) #int为定义整数型
"""
3
"""
>>> print(int(1.7))  #当int一个浮点型数时，int会保留整数部分
"""
1
"""
>>> print(float('1.3') + 2) #float()是浮点型，可以把字符串转换成小数
""""
3.3
""""
```


{% include google-in-article-ads.html %}

{% include assign-heading.html %}


print()和pprint()都是python的打印模块，区别是pprint()模块打印出来的数据结构更加完整，每行为一个数据结构，打印的输出结果更易阅读。特别是对于特别长的数据打印，print()输出结果都在一行，不方便查看，而pprint()采用分行打印输出，所以对于数据结构比较复杂、数据长度较长的数据，适合采用pprint()打印方式。
```python
>>> import pprint
>>> data = ("test", [1, 2, 3,'test', 4, 5], "This is a string!",
...         {'age':23, 'gender':'F'})
>>> print(data)
('test', [1, 2, 3, 'test', 4, 5], 'This is a string!', {'age': 23, 'gender': 'F'})
>>> pprint.pprint(data)
('test',
 [1, 2, 3, 'test', 4, 5],
 'This is a string!',
 {'age': 23, 'gender': 'F'})
```
更多pprint资料, 可参考[python数据格式化之pprint](https://blog.csdn.net/hxpjava1/article/details/73379642)
---------------------
