
# 循环

## for...in



```python
names = ['张三', '李四', '王五']
for name in names:
    print(name)
```

    张三
    李四
    王五


`range()`：生成整数序列

```python
range(101)    # 生成0至100的整数序列
range(1, 100)    # 生成1至99的整数序列
range(1, 100, 2)    # 生成1至99的奇数序列，2为步长
```

`list()`：转换成list列表


```python
print(list(range(5)))

#计算0～100的和
sum = 0
for x in range(101):
    sum += x
print(sum)
```

    [0, 1, 2, 3, 4]
    5050


## while

条件满足就不断循环，条件不满足就退出循环


```python
#计算0～100的奇数和

sum = 0
n = 99

while n > 0:
    sum = sum + n
    n = n - 2
print(sum)
```

    2500


`break`：提前退出循环




```python
n = 1

while n <= 100:
    if n > 10:
        break    #结束当前循环
    print(n)
    n += n
print('End')
```

    1
    2
    4
    8
    End


`continue`：跳出本次循环，直接开始下一次循环


```python
n = 0
while n < 10:
    n = n + 1
    if n % 2 > 0:
        continue    #结束本次循环，直接开始下次循环。跳过后面的print(n)
    print(n)
```

    2
    4
    6
    8
    10


要特别注意，不要滥用`break`和`continue`语句。`break`和`continue`会造成代码执行逻辑分叉过多，容易出错。大多数循环并不需要用到`break`和`continue`语句，上面的两个例子，都可以通过改写循环条件或者修改循环逻辑，去掉`break`和`continue`语句。

有些时候，如果代码写得有问题，会让程序陷入“死循环”，也就是永远循环下去。这时可以用Ctrl+C退出程序，或者强制结束Python进程。
