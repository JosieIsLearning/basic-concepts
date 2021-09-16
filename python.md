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
