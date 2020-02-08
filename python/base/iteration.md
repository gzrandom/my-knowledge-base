# 迭代

给定一个`list`或`tuple`，通过`for`循环来遍历这个`list`或`tuple`，这种遍历称为迭代（iteration）。

`for...in`循环不仅可用在`list`或`tuple`上，还可以作用在其他可迭代对象上。

`list`这种数据类型虽然有下标，但很多其他数据类型是没有下标的，但是，只要是可迭代对象，无论有无下标，都可以迭代，比如`dict`就可以迭代：

```python
>>> d = {'a':1, 'b':2, 'c':3}
>>> for key in d:
...     print(key)
...
a
b
c
```

通过`collections`模块的`Iterable`类型判断一个对象是否可迭代对象
```python
>>> from collections import Iterable
>>> isinstance('abc', Iterable)
True
>>> isinstance([1,2,3], Iterable)
True
>>> isinstance(123, Iterable)
False
```

实现下标循环，使用Python内置的`enumerate`函数可把一个`list`变成索引-元素对，可以在`for`循环中同时迭代索引和元素本身

```python
>>> for i, value in enumerate(['a', 'b', 'c']):
...     print(i, value)
...
0 a
1 b
2 c
```

在`for`同时引用两个变量：
```python
>>> for x,y in [(1,1), (2,4), (3,9)]:
...     print(x, y)
...
1 1
2 4
3 9
```