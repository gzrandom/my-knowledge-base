# sorted 排序算法

无论使用冒泡排序还是快速排序，排序的核心是比较两个元素的大小。如果是数字，可以直接比较，但如果是字符串或者两个dict呢？直接比较数学上的大小是没有意义的，因此，比较的过程必须通过函数抽象出来。

python内置`sorted()`函数可以对`list`进行排序
```python
>>> sorted([36, 5, -12, 9, -21])
[-21, -12, 5, 9, 36]
```

`sorted()`是一个高阶函数，可以接收一个`key`函数实现自定义的排序，例如按绝对值大小排序：
```python
>>> sorted([36, 5, -12, 9, -21], key=abs) 
[5, 9, -12, -21, 36]
```

字符串排序
```python
#默认情况下，字符串排序按ASCII大小比较，'Z' < 'a'，所以大写字母'Z'排在小写字母'a'前面
>>> sorted(['bob', 'about', 'Zoo', 'Credit'])
['Credit', 'Zoo', 'about', 'bob']
#把传入的字符串都变成大写字母（或小写字母），再排序，就可忽略大小写排序了
>>> sorted(['bob', 'about', 'Zoo', 'Credit'], key = str.lower)
['about', 'bob', 'Credit', 'Zoo']
#反向排序，不须改动key函数，可传入第三个参数'reverse=True'
>>> sorted(['bob', 'about', 'Zoo', 'Credit'], key = str.lower, reverse = True)
['Zoo', 'Credit', 'bob', 'about']
```