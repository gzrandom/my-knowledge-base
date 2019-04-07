
# list 与 tuple

## list

内置数据类型：列表

`list`是一种有序集合，可以随时添加或删除其中的元素

`len`：获取`list`元素的个数

使用索引号访问列表元素，索引号从`0`开始

用`-1`做索引表示最后一个元素。以此类推，`-2`，`-3`，`4`分别表示倒数第二，倒数第三，倒数第四个元素。


```python
classmate = ['张三', '李四', '王五']
print(classmate)
print(len(classmate))    #获取list元素个数
print(classmate[0])    #索引号从0开始
print(classmate[1])
print(classmate[2])
print(classmate[3])    #下标越界

```

    ['张三', '李四', '王五']
    3
    张三
    李四
    王五



    ---------------------------------------------------------------------------

    IndexError                                Traceback (most recent call last)

    <ipython-input-3-f59ab459aa27> in <module>
          5 print(classmate[1])
          6 print(classmate[2])
    ----> 7 print(classmate[3])    #下标越界
    

    IndexError: list index out of range



```python
print(classmate[-1])    #-1直接获取最后的元素
print(classmate[-2])    #倒数第二个元素
print(classmate[-3])
print(classmate[-4])    #下标越界
```

`append()`：追加元素到`list`末尾

`insert()`：把元素插入到指定位置

`pop()`：删除末尾元素

`pop(i)`：删除指定元素，`i`为索引号

替换某元素：直接对该元素赋值


```python
classmate.append('马六')
print(classmate)
classmate.insert(1, '陈二')
print(classmate)
classmate.pop()
print(classmate)
classmate.pop(2)
print(classmate)
classmate[1] = 'chener'
print(classmate)
```

    ['张三', '李四', '王五', '马六']
    ['张三', '陈二', '李四', '王五', '马六']
    ['张三', '陈二', '李四', '王五']
    ['张三', '陈二', '王五']
    ['张三', 'chener', '王五']


`list`里各元素数据类型可以不同

`list`的元素也可以是另一个`list`



```python
L = ['apple', 123, True]
s = ['java', 'c++', ['asp', 'php'], 'vb']
print('%s的长度是：%d' %(s, len(s)))
p = ['asp', 'php']
s = ['java', 'c++', p, 'vb']
print(s)
```

    ['java', 'c++', ['asp', 'php'], 'vb']的长度是：4
    ['java', 'c++', ['asp', 'php'], 'vb']


要访问'php'，可使用`p[1]`或`s[2][1]`

s可看作二维数组，类似的还有三维、四维数组...

空list：一个元素都没有，长度为0


```python
L = []
print(len(L))
```

    0


## tuple

元组：有序列表，一旦初始化就不能修改

没有`append()`、`insert()`这些方法，其它获取元素的方法跟`list`一样，但不能赋值。

不可变的`tuple`有什么意义？因为`tuple`不可变，所以代码更安全。如果可能，能用`tuple`代替`list`就尽量用`tuple`。

`tuple`的陷阱：当你定义一个`tuple`时，在定义的时候，`tuple`的元素就必须被确定下来


```python
classmate = ('张三', '李四', '王五')
print(classmate)
```

    ('张三', '李四', '王五')


定义空的`tuple`，可写成`()`


```python
t = ()
print(t)
```

    ()


但定义只有一个元素的`tuple`，如果这样定义：


```python
t = (1)
print(t)
```

    1


定义的不是`tuple`，是`1`这个数。这是因为括号`()`既可以表示`tuple`，又可以表示数学公式中的小括号，这就产生了歧义，因此，Python规定，这种情况下，按小括号进行计算，计算结果自然是`1`。

所以，只有1个元素的`tuple`定义时必须加一个逗号`,`，来消除歧义.

Python在显示只有1个元素的`tuple`时，也会加一个逗号`,`，以免你误解成数学计算意义上的括号。


```python
t = (1,)
print(t)
```

    (1,)


“可变”的`tuple`


```python
t = ('a', 'b', ['A', 'B'])
t[2][0] = 'X'
t[2][1] = 'Y'
print(t)
```

    ('a', 'b', ['X', 'Y'])


这个`tuple`定义的时候有3个元素，分别是`'a'`，`'b'`和一个`list`。不是说`tuple`一旦定义后就不可变了吗？怎么后来又变了？

别急，我们先看看定义的时候`tuple`包含的3个元素：

![tuple1](../pics/tuple1.png)

当我们把list的元素'A'和'B'修改为'X'和'Y'后，tuple变为：

![tuple1](../pics/tuple2.png)

表面上看，tuple的元素确实变了，但其实变的不是tuple的元素，而是list的元素。tuple一开始指向的list并没有改成别的list，所以，tuple所谓的“不变”是说，tuple的每个元素，指向永远不变。即指向'a'，就不能改成指向'b'，指向一个list，就不能改成指向其他对象，但指向的这个list本身是可变的！

理解了“指向不变”后，要创建一个内容也不变的tuple怎么做？那就必须保证tuple的每一个元素本身也不能变。

## 小结

list和tuple是Python内置的有序集合，一个可变，一个不可变。根据需要来选择使用它们。
