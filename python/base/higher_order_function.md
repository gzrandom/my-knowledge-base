# 高阶函数

## 变量可指向函数

```python
>>> abs(-10)    #abs(-10)是函数调用
10
>>> abs    #abs是函数本身
<built-in function abs>
>>> x = abs(-10)    #把结果赋值给变量
>>> x
10
>>> f = abs    #把函数本身赋值给变量
>>> f
<built-in function abs>
>>> f(-10)    #通过该变量调用这个函数
10
```

## 函数名也是变量

```python
>>> abs = 10    #函数指向10
>>> abs(-10)    #无法再通过abs(-10)调用该函数
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: 'int' object is not callable
>>>
```

代码绝对不能这样写，要恢复abs函数，重启python交互环境

注：由于`abs`函数实际上是定义在`import builtins`模块中的，所以要让修改`abs`变量的指向在其它模块也生效，要用`import builtins`; `builtins.abs = 10`。

## 传入函数

既然变量可以指向函数，函数的参数能接收变量，那么一个函数就可以接收另一个函数作为参数，这种函数就称之为高阶函数。

例：

```python
def add(x, y, f):
    return f(x) + f(y)
```

当我们调用```add(-5, 6, abs)```时，参数`x`，`y`和`f`分别接收`-5`，`6`和`abs`，根据函数定义，我们可以推导计算过程为：

```python
x = -5
y = 6
f = abs
f(x) + f(y) ==> abs(-5) + abs(6) ==> 11
return 11
```