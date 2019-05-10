# 切片

取一个`list`或`tuple`的部分元素。

```python
>>> L = ['Michael', 'Sarah', 'Tracy', 'Bob', 'Jack']
```

笨办法：

```python
>>> [L[0], L[1], L[2]]
['Michael', 'Sarah', 'Tracy']
```

循环：
```python
>>> r = []
>>> n = 3
>>> for i in range(n):
...     r.append(L[i])
... 
>>> r
['Michael', 'Sarah', 'Tracy']
```

切片(Slice)操作符：
```python
>>> L[0:3]
['Michael', 'Sarah', 'Tracy']
```
L[0:3]表示，从索引0开始取，直到索引3为止，但不包括索引3。即索引0，1，2，正好是3个元素。


```python
>>> L[:3]    //如果第一个索引是0，还可以省略
['Michael', 'Sarah', 'Tracy']
>>> L[1:3]    //也可以从索引1开始，取出2个元素出来
['Sarah', 'Tracy']
>>> L[-2:]    //从倒数第2个开始
['Bob', 'Jack']
>>> L[-2:-1]    //倒数第一个元素索引是-1
['Bob']
```