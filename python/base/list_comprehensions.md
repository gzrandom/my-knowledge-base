# 列表生成式

生成`list [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]`可以用`list(range(1, 11))`:
```python
>>> list(range(1, 11))
[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
```
要生成`[1x1, 2x2, 3x3, ..., 10x10]`怎么做？

方法1：循环

```python
>>> L = []
>>> for x in range(1, 11):
...    L.append(x * x)
...
>>> L
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```

方法2：列表生成式

```python
>>> [x * x for x in range(1, 11)]
[1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
```
写列表生成式时，把要生成的元素`x * x`放到前面，后面跟`for`循环，就可以把`list`创建出来

`for`循环后面还可以加上判断或嵌套循环：
```python
>>> [x * x for x in range(1, 11) if x % 2 == 0]    //加上判断，这样就可以筛选出仅偶数的平方
[4, 16, 36, 64, 100]
>>> [m + n for m in 'ABC' for n in 'xyz']    //可以使用两层循环，可以生成全排列
['Ax', 'Ay', 'Az', 'Bx', 'By', 'Bz', 'Cx', 'Cy', 'Cz']
```

`for`循环可以同时使用两个甚至多个变量，比如`dict`的`items()`可以同时迭代`key`和`value`
```python
>>> d = {'x': 'A', 'y': 'B', 'z': 'C' }
>>> for k, v in d.items():
...     print(k, '=', v)
...
x = A
y = B
z = C
```

列表生成式可以使用两个变量来生成`list`
```python
>>> d = {'x': 'A', 'y': 'B', 'z': 'C' }
>>> [k + '=' + v for k, v in d.items()]
['x=A', 'y=B', 'z=C']
```

把一个`list`中所有字符串变成小写
```python
>>> L = ['Hello', 'World', 'IBM', 'Apple']
>>> [s.lower() for s in L]
['hello', 'world', 'ibm', 'apple']
```

如果list中既包含字符串，又包含整数，由于非字符串类型没有lower()方法，所以列表生成式会报错
```python
>>> L = ['Hello', 'World', 18, 'Apple', None]
>>> [s.lower() for s in L]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
  File "<stdin>", line 1, in <listcomp>
AttributeError: 'int' object has no attribute 'lower'
```

使用内建的isinstance函数可以判断一个变量是不是字符串
```python
>>> x = 'abc'
>>> y = 123
>>> isinstance(x, str)
True
>>> isinstance(y, str)
False
```