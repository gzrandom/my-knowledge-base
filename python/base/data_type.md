
# 数据类型

## 1. 数据类型

* 整数

正、负整数：0, 100, -1000 等等

十六进制以0x前缀，0-9，a-f：0xff00, 0x270d等等

注意：Python的整数没有大小限制，而某些语言的整数根据其存储长度是有大小限制的，例如Java对32位整数的范围限制在-2147483648-2147483647。
   
* 浮点数

小数：1.2, 3.14, 0.007, -2.8

科学计数法：1.2e5, 3.14e-8

Python的浮点数也没有大小限制，但是超出一定范围就直接表示为inf（无限大）。

* 字符型

以单引号`'`或双引号`"`括起来的任意字符。`''`或`""`本身只是一种表示方式，不是字符串的一部分，因此，字符串'abc'只有a，b，c这3个字符。如果'本身也是一个字符，那就可以用""括起来，比如"I'm OK"包含的字符是I，'，m，空格，O，K这6个字符。

如果字符串内部既包含`'`又包含`"`怎么办？可以用转义字符\来标识，比如：

`'I\'m \"OK\"!'`

表示的字符串内容是：

`I'm "OK"!`

转义字符\可以转义很多字符，比如`\n`表示换行，`\t`表示制表符，字符`\`本身也要转义，所以`\\`表示的字符就是`\`，可以在Python的交互式命令行用print()打印字符串看看：


```python
print('I\'m ok.')
```

    I'm ok.



```python
print('I\'m learning\nPython.')
```

    I'm learning
    Python.



```python
print('\\\n\\')
```

    \
    \


如果字符串里面有很多字符都需要转义，就需要加很多`\`，为了简化，Python还允许用`r''`表示`''`内部的字符串默认不转义，可以自己试试：


```python
print('\\\t\\')
```

    \	\



```python
print(r'\\\t\\')
```

    \\\t\\


如果字符串内部有很多换行，用\n写在一行里不好阅读，为了简化，Python允许用'''...'''的格式表示多行内容，可以自己试试：


```python
print('''line1
... line2
... line3''')
```

    line1
    line2
    line3


上面是在交互式命令行内输入，注意在输入多行内容时，提示符由`>>>`变为`...`，提示你可以接着上一行输入，注意`...`是提示符，不是代码的一部分：

当输入完结束符`'''`和括号`)`后，执行该语句并打印结果。

如果写成程序并存为.py文件，就是：


```python
print('''line1
line2
line3''')
```

    line1
    line2
    line3


多行字符串`'''...'''`还可以在前面加上r使用，请自行测试：


```python
print(r'''hello,\n
world''')
```

    hello,\n
    world


* 布尔值

布尔值和布尔代数的表示完全一致，一个布尔值只有`True`、`False`两种值，要么是True，要么是False，在Python中，可以直接用`True`、`False`表示布尔值（请注意大小写），也可以通过布尔运算计算出来：

布尔值可以用and、or和not运算。

and运算是与运算，只有所有都为True，and运算结果才是True：
or运算是或运算，只要其中有一个为True，or运算结果就是True：
not运算是非运算，它是一个单目运算符，把True变成False，False变成True：


```python
3 > 2
```




    True




```python
True and False
```




    False




```python
True or False
```




    True




```python
not True
```




    False



* 空值

空值是Python里一个特殊的值，用None表示。None不能理解为0，因为0是有意义的，而None是一个特殊的空值。

## 2. type()函数

使用type()函数对变量类型进行检查

```python
a = 100
b = 12.345
c = 1 + 5j
d = 'hello, world'
e = True
print(type(a))
print(type(b))
print(type(c))
print(type(d))
print(type(e))
```

输出：
```python
<class 'int'>
<class 'float'>
<class 'complex'>
<class 'str'>
<class 'bool'>
```

## 3. 类型转换


- int()：将一个数值或字符串转换成整数，可以指定进制。
- float()：将一个字符串转换成浮点数。
- str()：将指定的对象转换成字符串形式，可以指定编码。
- chr()：将整数转换成该编码对应的字符串（一个字符）。
- ord()：将字符串（一个字符）转换成对应的编码（整数）。

