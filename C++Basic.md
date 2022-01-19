# 基础先修

## 计算机系统

由硬件、软件组成

**指令系统**是能够识别语言（机器语言的集合），是软硬件的主要界面

**计算机软件**：程序+文档。应用软件、系统软件、中间件

**计算机程序**：指令的序列，描述解决问题的方法和相关数据

## 计算机语言和程序设计方法的发展历史

- 发展历程

  - | 机器语言 | 二进制                 | 简单操作（加减法、数据移动） | 抽象                                     |
    | -------- | ---------------------- | ---------------------------- | ---------------------------------------- |
    | 汇编语言 | 助记符                 | 如ADD、SUB                   | 仍需考虑机器细节，抽象程度与机器语言一致 |
    | 高级语言 | 有含义的数据命名和算式 | 语句容易理解                 | 抽象层次高，屏蔽了机器底层细节           |


## C++语言

- C++是高级语言、面向对象编程OOP

    - 把所有事物看成对象，将同类对象抽象为类，类封装细节，只对外暴露最简单的接口，对象之间通过消息通信

- c++支持的程序设计方法

  | 语言             | 支持程度                   | 最初目的         | 主要工作                                 |
  | ---------------- | -------------------------- | ---------------- | ---------------------------------------- |
  | 面向过程         | 机器、汇编、高级语言都支持 | 用于数学计算     | 设计求解问题的过程                       |
  | 面向对象         | 由面向对象的高级语言支持   | 方便人的操作逻辑 | 一个系统由对象构成，对象之间通过消息进行 |
  | 泛型程序设计方法 |                            |                  |                                          |

## 面向对象的基本概念

1. 对象: 系统中用来描述客观事物的一个实体
2. 类：基于抽象与分类形成的，抽象出同一类对象的共同属性和行为，形成类
3. 封装：隐蔽对象的内部细节，对外形成一个边界，只保留有限的对外接口，使用方便，安全性好
4. 继承：可用于软件复用，改造、扩展已有类形成新的类
5. 多态：同样的消息作用在不同对象上有可能引起不同的行为，

## 程序的开发过程

- 源程序->目标程序
  - 汇编程序：汇编语言->目标程序
  - 编译程序：高级语言->
  - 解释程序：将高级语言源程序翻译成<u>机器指令</u>，边翻译边执行
    - NOTE: Java就是半编译半解释，为了跨平台
      - 先编译成二进制码，所有平台的Java虚拟机都可以识别，然后机子解释成本地可识别的二进制指令
- 开发过程
  - 算法与数据结构设计
  - 源程序编辑
  - 编译：语法检查，修改错误
  - 连接：把不同的模块、调用的程序库里的模块合在一起
  - 测试：用各种数据试，软件工程里有这课
  - 调试：找到错误原因，修改


## 信息的表示和储存

- 计算机的基本功能

  - 算数运算

  - 逻辑运算

### 计算机中的信息与存储单位

- 控制信息：指挥计算机操作
- 数据信息：
  - 数据信息
  - 非数据信息
- 存储单位：
  - 位b：最小单位，表示一位二进制信息
  - 字节B：8位二进制数字组成
  - 1KB=1024B
  - 1MB=1024KB
  - 1GB=1024M

### 计算机的数字系统

二进制系统：0，1

### 数据的编码表示

- 信息存储方式
  - 二进制：逻辑数据、字符也用
  - 原码
  - 补码：0的表示唯一；符号位可作为数值参与运算；结果仍为补码
  - 浮点数：用于表示小数
  - ASCII码：常用的西文字符编码
  - 汉字编码：GB 18030-2005

# 第一章 代码基本规范

- iostream

- 换行符：`cout << endl;`

- Token标记和空白

- 源代码风格

  - 每条语句占一行
- 每个函数都有开始和结束花括号
  - 函数中的语句都相对于花括号缩进
- 与函数名称相关的圆括号周围没有空白

# 第二章 基础介绍-C++语句

- definition: defining declaratio
	- 使用之前声明
	
- 赋值语句=
  - 从右向左进行
  
- 类简介

  - 一种数据类型和全部属性（包括使用它执行的操作）

    对象是根据这些描述创建的实体

cout的优势

  - 没有打印变量名，而是直接打印存储其中的整数值
  - 能够识别类型
  - `cout << "Now you have " << carrots << " carrots." <<endl;`

### cin

  - 从键盘输入的值赋给变量 `cin >> carrots;`

### 函数

#### 有返回值的函数

库文件里包含函数的编译代码->函数定义

头文件中包含了原型->函数接口

```c++
#include <iostream>
#include<cmath>

int main()
{
	using namespace std;
	double area, side;
	cout << "Enter the floor area, in square feet, of your home:";
	cin >> area;
	side = sqrt(area);
	cout << "This is the equivlant of a square"
		<< side
		<< " feet to the side." <<endl;
	cout << "How fascinating!"<<endl;
	return 0;
}
```

#### 函数变体

- 接受两个参数`pow()`
- 无返回值`void bucks(double)`不能将其放在赋值或其他语句中，而应在纯粹的函数调用语句中

#### 函数格式

定义独立，函数平等

- 函数头(原型)

    ```c++
    void simon(int n)
    ```

- 函数体

    ```c++
    type functionname(argumentlist)
    {
        statements
    }
    ```

- `using namespace std;`用哪放哪
  - 用的时候再说`std::cout << "I'sm using cout.";`

# 第三章 处理数据

## 简单变量

### 变量名

#### 命名规则：

- "字母 数字 _"only ==no hyphens allowed==
- 第一个字符不能是数字
- 区分大小写
- 不能将C++关键字作名称
- 形如__stop / _Dount保留给编译器及其资源的使用
- 形如_cost 用作全局标识符

信息存储在哪里

要存储什么值

存储何种类型的信息

#### 命名方案

- 漂亮的前缀
  - str，sz字符串
  - b布尔值
  - p指针
  - c单个字符

### 整型

char, short(16+), int(32,至少和short一样长), long(32+, 至少和int一样长), long long(64+, 至少和long一样长)

```c++
cout << "int is " << sizeof (int) << "bytes.\n";
cout << "short is " << sizeof (n_short) << "bytes.\n";
```

类型名使用sizeof加括号, 变量名括号可选

- climits中的符号常量
- 初始化`int owls=5`/`int wrens(432)` /`int hamburgers = {}`

### 无符号类型

unsigned int

关注整型溢出：32768

```c++
#include <iostream>
#include <climits>
#define ZERO 0
using namespace std;

int main()
{
	short sam = SHRT_MAX;
	unsigned short sue = sam;

	cout << "Sam has " << sam << " dollars ans Sue has " << sue << " dollars deposited.\n";
	cout << "Add $1 to each account.\n";
	sam = sam + 1;
	sue = sue + 1;
	cout <<"Now Sam has " << sam << " dollars ans Sue has " << sue << " dollars deposited.\n" << "Poor Sam!\n";
	sam = sue = ZERO;
	cout << "Sam has " << sam << " dollars ans Sue has " << sue << " dollars deposited.\n";
	cout << "Take $1 to each account.\n";
	sam = sam - 1;
	sue = sue - 1;
	cout << "Now Sam has " << sam << " dollars ans Sue has " << sue << " dollars deposited.\n" << "Lucky Sue!";
	return 0;
}
```

### 整型字面值

- O 八进制`cout << oct;`(改变显示整数的方式)
- Ox 十六进制`cout << hex;`

`int waist = Ox42;`直接写Ox就行，不用转换

默认显示十进制

### 布尔值bool

- true 1
- false 0

### const限定符

修改变量声明和<u>初始化</u>

`const int Months =12;` Months为常量

`const type name = value;`

## 浮点数

可表示小数值、非常大和非常小的值

### 小数点表示法

939001.32

### E表示法

`d.dddE+n` 指的是将小数点向右移N位

3.45E6

`8.33E-4` 除以10的乘方  不是乘以10的-4次

### 浮点类型

指数范围至少是(-37, 37)

float(32)

double(64)

long double(80/96/128)

# 复合类型

## 数组

### 创建的声明

- 存储在每个元素中的数值的类型
- 数组名
- 数组中的元素数

​	`typeName arrayname[arraySize]`

### 初始化

- 大括号

​	`double earnings [4]{1.2e4, 1.6e4, 1.1e4, 1.7e4}`;

## 字符串

- 字符串式
  - `char cat[8]={'f','a','t','\0'};`
  - `char fish[]="bubbles";`
- string式``

``` C++
char shirt_size='s';//字符串
char shirt_size="s";//字符串所在的内存地址
```

- 拼接字符串常量
- 在数组中使用字符串



