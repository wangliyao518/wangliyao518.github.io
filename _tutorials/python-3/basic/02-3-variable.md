---
bilibili_id: 
youku_id: XMzg1ODMwMzA1Mg
youtube_id:
description: 
chapter: 2
title: python变量
date: 2018-10-3

author: wang liyao
post-headings:
  - 变量赋值

---



{% include assign-heading.html %}

Python中的一个变量代表了一个实体，它的值可以随需要而改变。从概念上讲，它是一个保存实际值的内存位置。我们可以通过查询实体来检索代码中的值

但它需要给那个内存位置分配一个标签，这样我们就可以引用它了。我们把它叫做编程术语中的变量

下面是关于Python变量的一些关键事实。这些将帮助程序员有效地使用它们。

1.变量不需要声明。但是，您必须在使用前初始化它们。如:

```python
test = 1       #赋值 数字
print(test)
""""
1
""""

test = 'iphone 7 plus'   #赋值 字符串
print(test)
""""
iphone 7 plus
""""

```
2.上面的表达式将导致以下操作
- 创建一个对象来表示值1。
- 如果变量（test）不存在，那么它就会被创建。
- 变量与对象的关联，使它可以引用值

3.每当表达式发生变化时，Python都会将一个新对象（一大块内存）与变量关联起来，以引用该值。旧的就去垃圾回收器。
```python
>>> test = 10
>>> id(test)
1716585200
>>> test = 11
>>> id(test)
1716585232
>>> 
```
4.另外，为了优化，Python会构建一个缓存并重新使用一些不可变对象，比如小整数和字符串。

5.一个对象只是一个可以容纳以下内容的内存区域。
- 实际的对象值。
- 一种类型指示器，用于反映对象类型。
- 参考计数器，它决定了什么时候可以回收对象

6.一个变量可以在需要时容纳不同类型的对象。
```python
>>> test = 10
>>> type(test)
<class 'int'>
>>> test = 'techbeamers'
>>> type(test)
<class 'str'>
>>> test = {'Python', 'C', 'C++'}
>>> type(test)
<class 'set'>
>>> 
```

如果需要用多个单词来表示自变量，可以加上数字标致(中间可加下划线)，如`apple_2016='iphone 7 plus'` 请看代码

```python
apple_2016='iphone 7 plus and new macbook'
print(apple_2016)
""""
iphone 7 plus and new macbook
""""
```

一次定义多个自变量  `a,b,c=1,2,3`。

```python
>>> a, b, c = 1, 2, 3
>>> print(a, b, c)
1 2 3
>>>
```

一次交换变量。

```python
>>> a, b =1, 2
>>> b, a =a, b
>>> print(a, b)
2 1
>>>
```

