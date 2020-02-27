---
title: python中字符串和列表区别
date: 2018-08-31 22:20:16
tags: 
    - python
categories:
    - python
---

python中字符串和列表都是序列，但列表是可变的，其中的各项值可以用赋值语句修改。但字符串不可变。具体如下：

```python
>>> myList = [1,2,3,4]
>>> myList[2]
15
>>> myList[2] = 0
>>> myList
[1,2,0,4]
>>>myString = baby
myString[2]
b
myString[2] = i
Traceback (most recent call last):
File "<stdin>", line 1 ,in <module>
TypeError: 'str' object does not support item assignment
```

可见，字符串在尝试类似的操作时会产生错误。