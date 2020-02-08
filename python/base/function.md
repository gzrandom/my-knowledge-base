
# 函数

## 定义函数

以`def`语句定义函数

```
def 函数名(参数1, 参数2, ...):
    函数体
    return 返回参数1, 返回参数2, ...
```

如果没有`return`语句，函数执行完后返回`None`。`return None`可以简写为`return`。

若想调用其它文件中的函数，使用`from`导入。

例：函数my_func()保存在my_file.py文件内。


```
from my_file import my_func
```

语句中my_file是文件名，不包含.py扩展名。

## 空函数

定义什么都不做的函数，用pass语句，作占位符。

比如现在还没想好怎么写函数的代码，就可以先放一个pass，让代码能运行起来。

## 参数检查




```python
def my_abs(x):
    if x >= 0:
        return x
    else:
        return -x
    
my_abs(-9)
```




    9




```python
my_abs(1, 2)   //如果参数个数不对，会抛出TypeError
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-6-f9ac958f5dc5> in <module>
    ----> 1 my_abs(1, 2)
    

    TypeError: my_abs() takes 1 positional argument but 2 were given



```python
my_abs('a')
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-7-91ba0acb57cc> in <module>
    ----> 1 my_abs('a')
    

    <ipython-input-5-f2c80cbb5dfb> in my_abs(x)
          1 def my_abs(x):
    ----> 2     if x >= 0:
          3         return x
          4     else:
          5         return -x


    TypeError: '>=' not supported between instances of 'str' and 'int'



```python
abs('a')
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-4-f2001f88707b> in <module>
    ----> 1 abs('a')
    

    TypeError: bad operand type for abs(): 'str'



## 返回多个值

函数可以返回多个值

```python
import math

def move(x, y, step, angle = 0)
    nx = z + step * math.cos(angle)
    ny = y - step * math.sin(angle)
    return nx, ny

x, y = move(100, 100, 60, math.pi / 6)
print(x, y)

151.96152422706632 70.0

x = move(100, 100, 60, math.pi / 6)
print(x)

(151.96152422706632, 70.0)
```

其实这只是假象，python函数返回的仍然的单一值（tuple）。但在语法上，返回一个tuple可以省略括号，而多个变量可以同时接收一个tuple，按位置赋给对应的值