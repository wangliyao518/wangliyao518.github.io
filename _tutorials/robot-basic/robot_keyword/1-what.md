---
bilibili_id:
youku_id: 
youtube_id: 
description: "robot的keyword是 robot case调用的最小单元。 是robot case的一个小的step!"
chapter: 1
title: 什么是robot的 keyword
date: 2018-10-3
author: wang leo
post-headings:
  - 简短介绍
  - 使用类
  - 不实用类
  - 装饰器方法


---


{% include assign-heading.html %}

robot的keyword是 robot case调用的最小单元。 是robot case的一个小的step!
robot的keyword 在python层面可以理解为一个函数。

{% include assign-heading.html %}

在DemoLibrary的类中定义一个my_keyword的函数，它可以被当成keyword使用
```python
class DemoLibrary:
    def __init__(self, *args, **kwargs):
        print(f"Sample Library initialized with args: {args} and kwargs: {kwargs}")
 
    def my_keyword(self, *args, **kwargs):
        print(f"Keyword got args: {args} and kwargs: {kwargs}")
        return "Hello World"
```
使用的方式如下：
```python
*** Settings ***
Library    DemoLibrary.py

*** Test Cases ***
Use a Keyword with multiple arguments
    My Keyword    Argument 1    Argument 2    Named Argument=One Value
```


{% include assign-heading.html %}
当没有类的情况，我们只需要在一个python文件中定义函数即可，如下：
```python
import base64

def encode_as_base64(string):
    """
    Encode string as base64.
    """
    return base64.b64encode(string.encode())

def decode_from_base64(string):
    """
    Decode string from base64.
    """
    return base64.b64decode(string).decode()
```
使用时，library这个python文件，然后里面的函数就是keyword了。如下：
```python
*** Settings ***
Library    LibraryWithoutClass.py

*** Test Cases ***
Use Custom Keywords
    ${base64}    Encode As Base64    This is a Test String
    Log    ${base64}
    ${decoded}    Decode From Base64    ${base64}
    Log    ${decoded}

```


{% include assign-heading.html %}
装饰器模式来定义keyword则提供了一种方便的简单模式，它也很方便让我们“有选择”的暴露一些keyword给用户。
我们只需要在想暴露给用户的函数头上加上@keyword，不想暴露给用户函数加上@not_keyword，如：
```python
from robot.api.deco import keyword, not_keyword


@keyword('Login via user panel')
def login(username, password):
      # ...

@not_keyword
def this_is_not_keyword():
    pass
```

用装饰器还可以用来增加tags和参数的转化。如：
```python
from robot.api.deco import keyword


@keyword(tags=['tag1', 'tag2'])
def login(username, password):
    # ...

@keyword('Custom name', ['tags', 'here'])
def another_example():
    # ...

@keyword(types={'count': int, 'case_insensitive': bool})
def example_keyword(count, case_insensitive=True):
    if case_insensitive:
        # ...

@keyword(types=[int, bool])
def example_keyword(count, case_insensitive=True):
    if case_insensitive:
        # ...
```



