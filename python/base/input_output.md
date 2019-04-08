
# 输入输出

## 输出

### 屏幕输出print()


```python
print("hello world")
```

    hello world


多个字符串用逗号“,”分隔。遇到逗号会输出一个空格


```python
print("hello","world")
```

    hello world


打印整数


```python
print(300)
```

    300


计算结果


```python
print(100 + 300)
print("100 + 200 =", 100 + 300)
```

    400
    100 + 200 = 400


## 输入

### input()


```python
name = input()
```

    hello



```python
print(name)
```

    hello



```python
name = input("Please input your name:")
print("Hello", name)
```

    Please input your name:abc
    Hello abc



```python
print("1024 * 768 =", 1024 * 768)
```

    1024 * 768 = 786432


常见输入数值判断出现的错误


```python
birth = input('birth:')
if birth >= 2000:
    print('00后')
else:
    print('00前')
```

    birth:1998



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-1-b7f20b37e4ed> in <module>
          1 birth = input('birth:')
    ----> 2 if birth >= 2000:
          3     print('00后')
          4 else:
          5     print('00前')


    TypeError: '>=' not supported between instances of 'str' and 'int'


这是因为`input()`返回的数据类型是`str`，`str`不能直接和整数比较，必须先把`str`转换成整数。Python提供了`int()`函数来完成这件事情：


```python
s = input('birth:')
birth = int(s)
if birth >= 2000:
    print('00后')
else:
    print('00前')
```

    birth:1998
    00前


如果输入非数值'abc'，还是会出现错误。

因为`int()`遇到非数值型会报错


```python
s = input('birth:')
birth = int(s)
if birth >= 2000:
    print('00后')
else:
    print('00前')
```

    birth:abc



    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    <ipython-input-4-bd17290f9ba0> in <module>
          1 s = input('birth:')
    ----> 2 birth = int(s)
          3 if birth >= 2000:
          4     print('00后')
          5 else:


    ValueError: invalid literal for int() with base 10: 'abc'



```python

```
