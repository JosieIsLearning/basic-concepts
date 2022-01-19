# 一、python基础

IPython

NumPy Python科学计算的基础包

SciPy 解决各种标准问题域的模块的集合

Pandas 数据分析

Matplotlib 绘制数据图表的库

scikit-learn 数据挖掘的数据分析工具

Spyder 交互式的语言开发环境

## 基本组成

### 模块

即.py，一个文件就是一个模块

`import turtle`导入模块语句

`turtle.pencolor("res")`为调用turtle库中的函数语句，也是主程序语句块

### 语句

- 语句是Python程序的过程构造块，用于创建对象、变量赋值、调用函数、控制分支、循 环结构等，语句包含表达式，而表达式是由操作数和运算符构成，用于创建和处理对象
- Python使用缩进表示语句块的开始和结束。Python中凡是语句结尾用冒号（:）标识时，下面的 语句必须缩进4个空格或者用Tab键实现，但两者不混用；语句块中每一个语句的缩进量相同；当减 少缩进时，则表示当前语句块退出或结束

变量直接`print(s)`

### 关键字和标识符

#### 关键字

```python
>>> import keyword
>>> keyword.kwlist
['False''None''True','and','as','assert','break','class','continue','def','del','elif','else','except','finally','for','from','global','if','import','in','is','lambda','nonlocal','not','or','pass','raise','return','try','while','with','yield']
```

#### 标识符

- python区分大小写，由英语字母、数字和下划线组成
- 避免使用双下划线，第一个是字母/下划线
- 用#注释

### 表达式

`eval`定义字符串

## 数据类型

### 数值数据类型

1. 整数 int
   1. 二进制0b, 八进制0o, 十六进制0x

      > 0B101, 0O777, 0X89AB
2. 布尔类型BOOL true/false  (可做==and or not==运算)
3. 浮点类型float
4. 复数类型complex，一般形式为x+yj，用real和imag属性分别获得实部和虚部

```python
>>> 1.234E-2+5.67E5j.real
0.01234
>>> 1.234E-2+5.67E5j.imag
567000.01234
```

### 字符串数str  单、双、三引号

- ```python
  >>>eval(input("姓名年龄"))
  >>>print(eval("1+2"))
  ```

- ```python
  age=5; b=10;c=age-b;
  print(c)
  ```

- 字符串基本操作符

  - a+b 链接两个字符串
  - a * n 或 n * a 复制N次字符串
  - a in s  如果a是s的子串，返回True，否则返回False
  - str[i] 索引，返回第i个字符
  - str[N:M] 切片，返回第N到第M的子串，其中不包含M

### 转义字符

和C语言一样

### 复合数据类型

#### 列表

有序，可被操作

```python
list1=[1,2,3,"小明",178.9,[101,25]]
list2=["A","B","C","D","E"]
#增补
list1.append(100)
list2+["G"]
list2.insert(3,"g")
list2*2 #一样的字符再来一遍
#删除
del list4[1]
list4.remove()
#检查列表元素
"H" in list2
True/False
```



#### 元组

不可被操作，()

#### 字典

```python
d1={"id":10,"name":"liili","class":"A01"}
```



## 运算类型

算数运算

关系运算

逻辑运算

赋值运算

| 运算符号 | 含义     | 说明                         | 实例    | 结果 |
| -------- | -------- | ---------------------------- | ------- | ---- |
| **       | 乘幂     | 操作数的乘幂                 | n**3    | 512  |
| *        | 乘法     | 操作数的积                   | n* n *2 | 128  |
| /        | 除法     | 左操作数除以右操作数         | 10/n    | 1.25 |
| //       | 整数除法 | 两个整数相除，结果为整数     | 10//n   | 1    |
| %        | 模数     | 左操作数除以右操作数后的余数 | 10%n    | 2    |
| +        | 加法     | 两个操作数之和               | 10+n    | 18   |
| -        | 减法     | 左操作数减去右操作数         | n-10    | -2   |

(n取8)，和数学运算中运算符的优先级一样

## 程序的基本类型

![image-20210907183813926](https://user-images.githubusercontent.com/73213476/133541670-6bfd23ec-5ac6-46a6-be17-1b3110280b71.png)

- 顺序结构

- 分支结构

  ```python
  consume = eval(input("输入消费金额"))
  flag = eval(input("输入是否会员编号（2：金卡会员，1：普通会员，其他：非会员）:"))
  if flag == 2:
      consume *= 0.9
  elif flag == 1:
      consume *=0.95
  else:
      consume *= 0.99
  print("用户应付：{}".format(consume))
  ```

  `else if`直接写成`elif`,你说急不急人

  无括号，靠缩进表示在结构内

- 循环语句

  - break
  - continue

  ## 函数

  是对程序逻辑进行结构化或过程化的一种编程方法

  ```python
  def 函数名(形式参数):
      函数执行体语句序列
      return[表达式]
  ```

  lambda函数

  ```python
  <函数名>=lambda<参数列表>
  ```
![](函数.assets/image-20211109183902779.png)

![image-20211109184007388](函数.assets/image-20211109184007388.png)

# 程序的基本语句

## 1. <a name='pass'></a>pass

非操作语句，作为空白字符划定代码块

## 2. <a name='range'></a>range(起点，终点，步进)

返回一个迭代器，产生一个均匀分布的整数序列

```python
range(10)
list(range(10))
```

[1,2,3,4,5,6,7,8,9,10]

# 程序的基本结构

顺序结构

分支结构

```python
consume=eval(input("输入消费金额"))
flag=eval(input("输入是否会员编号（2：金卡会员，1：普通会员，其他：非会员）:"))
if flag == 2:
    consume *= 0.9
elif flag == 1:
    consume *=0.95
else:
    consume *= 0.99
print("用户应付：{}".format(consume))
```

循环结构

- for 遍历循环，可以提前确定循环次数

```python
n=eval(input("请输入<1000的整数："))
s=0
for i in range(1,n+1):
    s+=i
print(s)
```

- while条件循环，根据判断条件确定是否执行循环

```python
x=256;
total = 0;
while x> 0;
    if total >500:
        break
    total +=x
    x = x//2
```

- break 跳出当前整个循环，脱离该循环后，程序继续执行循环后的语句
- continue 结束本次循环，但不终止当前整个循环，还会继续判断下一次循环的条件是否成立

# 函数

```python
def 函数名(形式参数):
    函数执行体语句序列
    return[表达式]
```

•“def”为关键字，代表函数的定义开始

•“函数名”为定义的函数名称，命名必须符合标识符的定义规则，作为以后被调用时的具体名称

•圆括号之间用于定义形式参数，简称形参，“形式参数”为可选项；

- 任何传入的参数和自变量必须放在圆括号中间。圆括号不可省略。

冒号也必须存在，表明函数的正式内容从冒号后起始。

==在第一个return语句结束==

## 3. <a name=''></a>例子

### 3.1. <a name='input'></a>input输入函数

从键盘读取输入数据，并返回一个字符串（注意，返 回值不是数值）

<u>注：当用input同时输入多个数据时，用逗号隔开。当输入的数据是字符串时，输入字符串要 用单引号或双引号括住，如下面的例子</u>

```python
age=int(input("请输入你的年龄："))
print(age)
```

### 3.2. <a name='eval'></a>eval(<字符串>)

能将字符串当成有效的表达式来求值并返回计算结果

```python
eval(input("请输入你的姓名和年龄："))

print(eval("1+2"))
```

### 3.3. <a name='print'></a>print()输出函数

向屏幕输出数据，可以通过用逗号分隔0个或多个表达式

将表达式转换为字符串输出

```python
age=25
print("我的年龄=",age)
我的年龄=25
```

### 3.4. <a name='lambda'></a>lambda   匿名函数

用于定义简单的、能够在一行内表示的函数，返回一个函数类型

```python
<函数名> = lambda <参数列表> : <表达式>

f= lambda x,y:x+y
print(f(10,20))
30
```

该ppt第50页了

# 函数库

## 4. <a name='Python'></a>Python函数类型

### 4.1. <a name='-1'></a>内置函数

启动后就可以调用，不需要import导入

![image-20210928204805760](函数.assets/image-20210928204805760.png)

### 4.2. <a name='-1'></a>标准函数

运行后需要用import导入才能调用

### 4.3. <a name='-1'></a>自定义函数

由程序员在程序中定义，然后才能在程序中调用

### 4.4. <a name='-1'></a>外部库函数

外部库函数不是Python自带的函数，也称为第三方库的函数，需要采用pip工具从网络下载和安装， Python运行后也不会启动，需要由import导入，然后才能在程序中调用。

# pandas

相当于一个excel表，字符串，时间序列等的数据处理，是numpy的延申，爬虫，数据清洗

## 5. <a name='series'></a>series

### 5.1. <a name='introduction'></a>introduction

创建

```python
import pandas as pd
import numpy as np
```

## 6. <a name='DataFrame'></a>DataFrame

表格型数据结构

# 第三章 python的数据结构、函数和文件

## 7. <a name='-1'></a>数据结构和序列

### 7.1. <a name='-1'></a>元组

#### 7.1.1. <a name='-1'></a>基本定义

```python
#定长，不可改变，用逗号分隔一列值即可
tup = 4，5，6
#复杂时最好将值放到圆括号里
nested-tup = (4,5,6),(7,8)
#tuple可以将任意序列转换成元组
tuple([4,0,2])
tup=tuple('string')
#可用方括号访问元组中的元素，从0开始
tup[0]
```

#### 7.1.2. <a name='-1'></a>修改

```python
#有对象可变
tup[1].append(3)
#可以使用+号链接元组来生成更长的元组
(4,none,'foo')+(6,0)+('bar',)
```

- 乘以整数会生成多份拷贝的元组

#### 7.1.3. <a name='-1'></a>元组拆包

最终4,5,6分别和a,b,c对应

```python
tup=(4,5,6)
a,b,c=tup
```

#### 7.1.4. <a name='-1'></a>元组方法

元组的内容和长度无法改变，用count计量某数值出现的次数

### 7.2. <a name='-1'></a>列表

- 命名   `a_list=[2,3,7,None]` 
- 增减元素`b_list.append('dwarf')`
- 插入指定位置`b_list.insert(1,'red')`
- 移除符合要求的值`b_list.remove('foo')`
- 移除特定位置的元素(删去)`b_list.pop(2)`
- 连接和联合列表`[4,None,'foo']=[7,8,(2,3)]`
- 已有一个列表x，向其添加元素`x.extend([7,8,(2,3)])`

```python
#修改，peekaboo将会替换bar
tup=('foo','bar','baz')
b_list=list(tup)
b_list[1]='peekaboo'

#列表内部排序
a=[7,2,5,3,6]
a.sort()
```

### 7.3. <a name='-1'></a> 内建序列函数

- enumerate

- sorted(), 返回一个根据任意序列中的元素新建的已排序列表

- zip将列表、元组或其他序列的元素配对，新建一个元组构成的列表

  ```
  seq1=['foo','bar','baz']
  seq2=['one','two','three']
  zipped=zip(seq1.seq2)
  list(zipped)
  
  [('foo','one'),('bar','two'),('baz','three')]
  ```

- reversed 倒序排列

### 7.4. <a name='-1'></a>字典

需要为不可变的对象`empty_dict={}`

`d1={'a':'some value',b':[1,2,3,4]}`

- 插入字典中的元素 `d1[7]='an integer'`
- del关键字/pop方法删除值

```python
del d1[5]
#或
ret=di.pop('dummy')
```

- 合并字典 ，会覆盖已有的键值`d1.update({'b':'foo,'c':12})`

- 将列表作为键使用：转换为元组

  ```python
  d={}
  d[tuple([1,2,3])]=5
  ```

### 集合

只有键，没有值

- 创建`set([2,2,2,1,3,3])` 或者`{2,2,3,4,1,}`

- 联合，形成并集

  ```python
  a.union(b)
  a|b#均形成a,b集合
  ```

- 交集 `a.intersection(b)`或`a & b`

- 转换为元组`my_set={tuple(my_data)}`

## 文件与操作系统

- 打开文件进行读写，

  ```python
  path='examples/segismundo.txt'
  f=open(path)
  ```

- 转移句柄 `f.seek(3)   f.read(1)`

- 关闭文件 `f.close()`

# Numpy

## ndarray

一个通用的多维同类数据容器，有shape属性

### 生成ndaray

- 用array函数，生成numpy数组

  ```python
  data1=[5,32,6,8,2,7]
  arr1 = np.array(data1)
  ```

- 嵌套序列变多维数组

- astype 显示转换数组的数据类型 `arr.dtype`

### numpy数组算术

- 逐元素操作

```python
arr=np.array([1,2,3],[4,5,6])
arr * arr


out: array([[1,4,9],[16,25,36]])
```

- 基础索引与切片

```python
arr = np.arange(10)
arr[5:8]
arr

out: array([0,1,2,3,4,12,12,12,8,9])    
```

- 数组的切片索引

  - ```python
    arr
    array([0,1,2,3,4,64,64,8,9])
    arr[1:6]
    ```

    out:([1,2,3,4,64])

    ```
    
    ```

- 二维数组切片:沿着轴0进行切片

  - ```python
    #arr2d= array([[1,2,3],[4,5,6],[7,8,9]])
    arr2d[:2]
    array([[1,2,3],[4,5,6]])
    ```

- 布尔索引

  布尔运算也是矢量的，比如以下代码：

  ```python
  a1 = np.arange(0,24).reshape((4,6))
  print(a1<10) #会返回一个新的数组，这个数组中的值全部都是bool类型
  > [[ True  True  True  True  True  True]
   [ True  True  True  True False False]
   [False False False False False False]
   [False False False False False False]]
  ```

  这样看上去没有什么用，假如我现在要实现一个需求，要将`a1`数组中所有小于10的数据全部都提取出来。那么可以使用以下方式实现：

  ```python
  a1 = np.arange(0,24).reshape((4,6))
  a2 = a1 < 10
  print(a1[a2]) #这样就会在a1中把a2中为True的元素对应的位置的值提取出来
  ```

- 神奇索引

  ## 通用函数
