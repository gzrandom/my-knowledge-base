# map/reduce

## map()

`map()`函数接收两个参数：`函数`, `Iterable`

`map()`将传入的`函数`依次作用到`序列`的每个元素，并把结果结果作为新的`Iterable`返回。

例 ：

函数f(x)=x<sup>2</sup>，要把这个函数作用在一个`list [1, 2, 3, 4, 5, 6, 7, 8, 9]`上，用`map()`实现：

```python
>>> def f(x):
...     return x * x
...
>>> r = map(f, [1, 2, 3, 4, 5, 6, 7, 8, 9])
>>> list(r)
[1, 4, 9, 16, 25, 36, 49, 64, 81]
```

`map()`传入的第一个参数是`f`，即函数对象本身。由于结果`r`是一个`Iterator`，`Iterator`是惰性序列，因此通过`list()`函数让它把整个序列都计算出来 并返回一个`list`。

直接用循环实现：

```python
>>> for n in [1, 2, 3, 4, 5, 6, 7, 8, 9]:
...     L.append(f(n))
...
>>> print(L)
[1, 4, 9, 16, 25, 36, 49, 64, 81]
```
两者功能一样，但循环代码不能一眼看明白“把f(x)作用在list每一个元素并把结果生成一个新的list”

所以，`map()`作为高阶函数，更事实上它把运算规则抽象了。因此，不但可以计算简单的f(x)=x<sup>2</sup>，还可以计算任意复杂的函数。

比如：把这个`list`所有数字转为字符串

```python
>>> list(map(str,  [1, 2, 3, 4, 5, 6, 7, 8, 9]))
['1', '2', '3', '4', '5', '6', '7', '8', '9']
>>>
```

## reduce()

`reduce()`是一个函数作用在一个序列`[x1, x2, x3, ...]`上，这个函数必须接收两个参数，`reduce`把结果继续和序列的下一个元素做累积计算。效果如下：

```python
reduce(f, [x1, x2, x3, x4]) = f(f(f(x1, x2), x3), x4)
```

例：一个序列求和

```python
>>> list(map(str,  [1, 2, 3, 4, 5, 6, 7, 8, 9]))
['1', '2', '3', '4', '5', '6', '7', '8', '9']
>>> from functools import reduce
>>> def add(x, y):
...     return x + y
...
>>> reduce(add, [1, 3, 5, 7, 9])
25
>>>
```

当然求和运算可以直接用python内建函数`sum()`，没必要用`reduce`。

但如果把序列`[1, 3, 5, 7, 9]`变换成整数`13579`，`reduce`就可以派上用场：

```python
>>> from functools import reduce
>>> reduce(add, [1, 3, 5, 7, 9])
25
>>> from functools import reduce
>>> def fn(x, y):
...     return x * 10 + y
...
>>> reduce(fn, [1, 3, 5, 7, 9])
13579
```

这个例子本身没多大用处，但是，如果考虑到字符串`str`也是一个序列，对上面的例子稍加改动，配合`map()`，我们就可以写出把`str`转换为`int`的函数：

```python
>>> from functools import reduce
>>> def fn(x, y):
...     return x * 10 + y
...
>>> def char2num(s):
...     digits = {'0': 0, '1': 1, '2': 2, '3': 3, '4': 4, '5': 5, '6': 6, '7': 7, '8': 8, '9': 9}
...     return digits[s]
...
>>> reduce(fn, map(char2num, '13579'))
13579
```

整理成一个`str2int`的函数就是

```python
>>> from functools import reduce
>>> DIGITS = {'0': 0, '1': 1, '2': 2, '3': 3, '4': 4, '5': 5, '6': 6, '7': 7, '8': 8, '9': 9}
>>> def str2int(s):
...     def fn(x, y):
...         return x * 10 + y
...     def char2num(s):
...         return DIGITS[s]
...     return reduce(fn, map(char2num, s))
...
>>> str2int('13579')
13579
```

还可以用`lambda`函数进一步简化：

```python
>>> from functools import reduce
>>> DIGITS = {'0': 0, '1': 1, '2': 2, '3': 3, '4': 4, '5': 5, '6': 6, '7': 7, '8': 8, '9': 9}
>>> def char2num(s):
...     return DIGITS[s]
...
>>> def str2int(s):
...     return reduce(lambda x, y: x * 10 + y, map(char2num, s))
...
>>> str2int('13579')
13579
```

也就是说，假设Python没有提供`int()`函数，你完全可以自己写一个把字符串转化为整数的函数，而且只需要几行代码！