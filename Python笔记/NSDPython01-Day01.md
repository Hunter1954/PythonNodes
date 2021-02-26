# Python01-Day01

张老师gitee地址：https://gitee.com/mrzhangzhg/nsd2020/

Guido van Rossum 于1989年底创建了python，91年初，python发布了第一个公开发行版

为了更好的完成荷兰的CWI（国家数学和计算机科学研究院）的一个研究项目而创建

## Python的特点

- 高级：有高级的数据结构，缩短开发时间与代码量
- 面向对象：为数据和逻辑相分离的结构化和过程化编程添加了新的活力
- 可升级：提供了基本的开发模块，可以在它上面开发软件，实现代码的重用
- 可扩展：通过将其分离为多个文件或模块加以组织管理

- 可移植性：python是用C写的，又由于C的可移植性，使得python可以运行在任何带有ANSI C编译器的平台上
- 易学：python关键字少、结构简单、语法清晰
- 易读： 没有其他语言通常来访问变量、定义代码块和进行模式匹配的命令符号
- 内存管理器：内存管理是由python解释器负责的

## Python运行方式

### 交互式

- 进入交互式解释器

  ```bash
  [root@python ~]# python3
  Python 3.6.8 (default, Nov 16 2020, 16:55:22) 
  [GCC 4.8.5 20150623 (Red Hat 4.8.5-44)] on linux
  Type "help", "copyright", "credits" or "license" for more information.
  >>> print('hello world')
  hello world
  >>> 
  ```

- 退出交互式解释器

  ```bash
  >>> exit()
  或
  >>> "Ctrl+d"
  ```

### 文件形式

- 明确指定解释器

  ```bash
  [root@python ~]# python3 hello.py
  ```

- 赋予python文件可执行权限

  ```bash
  [root@python ~]# chmod +x hello.py
  [root@python ~]# ./hello.py
  ```

## Python 语法结构

### 语句块缩进

- python官方手册：https://docs.python.org/zh-cn/3.6/library/index.html

- Python缩进表达代码逻辑，建议缩进4个空格
- 注释、续行和同行多条语句与shell一样，在pycharm中，选中多行，按Ctrl+/进行注释或取消注释

### 输出语句

- 在python中主要使用print实现输出，print是一个函数

- 在python中函数调用需要添加()，括号内是传给函数的参数

  ```bash
  >>> print("hello world!")   # 打印一个字符串，单双引号没有区别，但是必须有
  hello world!
  # 在print函数的()中，输入的是参数，各个参数之间用逗号隔开
  >>> print("hao", 123)       # 打印字符串和数字
  hao 123
  # print函数输出的各项之间，默认用空格分隔，可以通过sep指定分隔符
  >>> print("hao", 123, "abc")
  hao 123 abc
  >>> print("hao", 123, "abc", sep="***")
  hao***123***abc
  ```

## 输入语句

- python中，通过input函数获取用户键盘输入

- input函数的参数是字符串，他是屏幕提示语
  ```bash
  # 变量赋值，=两边空格可有可无
  >>> user = input('username: ')   # 用户输入内容保存到变量user中
  username: tom
  >>> user    # 使用变量
  'tom'
  
  # input读入的数据都是字符串类型。相同类型的数据才能运算
  >>> num = input("number: ")
  number: 10
  >>> num + 5    # num是字符串，不能和数字进行运算
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: must be str, not int
  >>> type(num)    # 查看num的类型
  <class 'str'>
  >>> int(num) + 5  # int函数将字符串转成整数
  15
  >>> num + str(5)  # str函数将对象转成字符串
  '105'
  >>> num + "5"
  '105'
  ```

## 变量

- 字面量就是看到什么是什么，如'abc',100

- 变量是变化的量，看到什么不一定是什么

- 变量只是为了编写代码方便。当看到变量是，应该透过变量看到它代表的值

- 编写代码是尽量多的使用变量，而不是直接使用字面量。直接使用字面量，是硬编码。代码可复用性差

- 变量名称约定

  - 第一个字符只能是大小写字母或下划线
  - 后续字符只能是大小写字母、数字、下划线
  - 曲分大小写

- 推荐采用的命令方法

  - 变量名全部采用小写字母，如：pythonstring
  - 简短、有意义，如py_str
  - 变量名全部采用小写字母，如pythonstring
  - 多个单词间用下划线分割，如py_str
  - 变量名用名词，函数名用谓词（动词+名词），如phone/update_phone
  - 类名采用驼峰形式，如MyClass

- 变量在使用之前，必须先进行赋值

- 变量赋值是一个自右向左的运算，将=右边表达式的计算结果，赋值给左边的变量

  ```bash
  >>> a = 10 + 5
  >>> a
  15
  ```

- 变量支持重新赋值

  ```bash
  >>> a = 20
  >>> a = a + 10   # 将a+10的结果再赋值给a
  # 以上代码可以简写为
  >>> a += 10
  # 根据以上写法，举一反三
  >>> a -= 20
  >>> a
  20
  >>> a *= 2
  >>> a
  40
  ```

- 注意：Python不支持诸如i++ / i--之类的操作

  ```bash
  >>> a = 40
  >>> ++a     # 正正为正
  40
  >>> --a     # 负负为正
  40
  >>> import this    # 导入python之禅
  The Zen of Python, by Tim Peters
  
  Beautiful is better than ugly.     美胜丑
  Explicit is better than implicit.  明胜暗
  Simple is better than complex.     简胜繁
  ```

## 运算符

### 算术运算符

```bash
# 加减乘正常运算
# /是真正的除法
>>> 5 / 3
1.6666666666666667
# //只保留商
>>> 5 // 3
1
# %是模运算，即求余
>>> 5 % 3
2
# **是幂运算
>>> 2 ** 3
8
# 通过round函数实现四舍五入
>>> round(5 / 3)     # 5/3，默认保留到整数部分
2
>>> round(5 / 3, 2)  # 精确到小数点后2位
1.67
# 精准的数学中，是4舍6入5成双 ！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！！
>>> round(5 / 2)  # 2.5取双数，所以结果是2
2
# divmod函数，可以同时得到商和余数
>>> divmod(5, 3)
(1, 2)
>>> a, b = divmod(5, 3)  # 商和余数分别赋值给a和b
>>> a
1
>>> b
2
```

### 比较运算符

``` bash
# 判断是否相等使用==
>>> 3 == 3
True    # True是关键字，表示真
# 判断是否不相等使用!=
>>> 3 != 3
False    # False是关键字，表示假
# python支持连续比较
>>> 10 < 20 < 30
True
# 不推荐以下这种写法
>>> 10 < 20 > 15
True   (这里分别对10和20 及 20和15 进行了比较)
```

### 逻辑运算符

```bash
# and两边表达式结果全为True，最终才为True
>>> 10 < 20 and 20 > 15
True
# or两边表达式结果全为False，最终才为False
>>> 10 < 20 or 20 > 100
True
>>> 100 < 20 or 20 > 100
False
# not是单目运算符，将真变假，将假变真
>>> 20 > 10
True
>>> not 20 > 10
False
```

## 数据类型

- 内置函数：https://docs.python.org/zh-cn/3.6/library/functions.html

### 数字

- 整数：没有小数点

- 浮点数：有小数点

- 布尔数：True为1，False为0

  ```bash
  >>> True + 1
  2
  >>> False * 5
  0
  ```

- 整数在不同进制下的表示方法

  ```bash
  # python默认以10进制表示数字
  >>> 11
  11
  # 8进制以0o或0O开头
  >>> 0o11
  9   # 默认以10进制输出
  # 16进制以0x或0X开头
  >>> 0x11
  17
  # 2进制以0b或0B开头
  >>> 0b11
  3
  
  # 2小时3分5秒是多少秒？
  >>> 2 * 60 * 60 + 3 * 60 + 5
  7385
  # 0x235 转成10进制怎么算？ 
  >>> 2 * 16 * 16 + 3 * 16 + 5
  565
  >>> 0x235
  565
  # 0o235 转成10进制怎么算？ 
  >>> 2 * 8 * 8 + 3 * 8 + 5
  157
  >>> 0o235
  157
  
  # 10000秒是几小时几分几秒？
  >>> divmod(10000, 60)
  (166, 40)  -> 166分40秒
  >>> divmod(166, 60)
  (2, 46)    -> 2小时46分
  
  # 10000转换成16进制数是？
  >>> divmod(10000, 16)
  (625, 0)
  >>> divmod(625, 16)
  (39, 1)
  >>> divmod(39, 16)
  (2, 7)
  # 10000 -> 0x2710
  >>> hex(10000)
  '0x2710'
  ```

### 字符串

- python中字符串被定义为引号之间的字符集合

- python支持使用成对的单引号或双引号

- 无论单引号，还是双引号，表示的意义相同

- python还支持三引号（三个连续的单引号或者双引号），可以用来包含特殊字符

  ```bash
  >>> s1 = """tom
  ... jerry
  ... jack
  ... rose
  ... """
  >>> print(s1)
  tom
  jerry
  jack
  rose
  
  >>> s1
  'tom\njerry\njack\nrose\n'
  >>> s2 = "bj\ntj\nxa\nzz"
  >>> print(s2)
  bj
  tj
  xa
  zz
  ```

- 常见操作

  ```bash
  >>> s1 = 'python'
  >>> len(s1)   # 取长度
  6
  >>> s1[0]     # 第一个字符，下标为0
  'p'
  >>> s1[6]     # 下标为6，超出范围，报错
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  IndexError: string index out of range
  >>> s1[5]
  'n'
  >>> s1[-1]  # 负数表示从右向左，最右的一个字符
  'n'
  >>> s1[-6]  # 自右向左第6个字符
  'p'
  >>> s1[2:4]  # 切片，起始下标包含，结束下标不包含
  'th'
  >>> s1[2:6]  # 切片时，下标超出范围是允许的
  'thon'
  >>> s1[2:600]
  'thon'
  >>> s1[2:]   # 结束下标不写，表示取到结尾
  'thon'
  >>> s1[:2]   # 起始下标不写，表示从开头取
  'py'
  >>> s1[:]    # 从开头取到结尾
  'python'
  >>> s1[::2]  # 步长值为2，取切片
  'pto'
  >>> s1[1::2]
  'yhn'
  >>> s1[::-1]  # 步长为负，表示自右向左取
  'nohtyp'
  
  
  >>> 't' in s1          # t在s1中吗？
  True
  >>> 'th' in s1         # th在s1中吗？
  True
  >>> 'to' in s1         # to在s1中吗？
  False
  >>> 'to' not in s1     # to不在s1中吗？
  True
  
  >>> s1 + ' is good'    # 字符串拼接
  'python is good'
  >>> '*' * 30   # 字符串*重复30遍
  '******************************'
  >>> '#' * 30
  '##############################'
  >>> s1 * 3
  'pythonpythonpython'
  ```

  

### 列表

- 列表可以当作数组使用

- 字符串的相关操作同样适用于列表

  ```bash
  >>> l1 = [10, 20, 5, 30, 8]
  >>> len(l1)
  5
  >>> l1[0]
  10
  >>> l1[2:4]
  [5, 30]
  >>> 20 in l1
  True
  >>> l1.append(20)   # 向列表尾部追加数字20
  >>> l1
  [10, 20, 5, 30, 8, 20]
  ```

## 元组

- 可以理解为元组是不可变的列表

- 列表的相关操作同样适用于元组

  ```bash
  >>> t = (10, 20, 8, 38)
  >>> len(t)
  4
  >>> 10 in t
  True
  >>> t[2]
  8
  
  >>> l1[0] = 100   # 将列表第一项改为100
  >>> l1
  [100, 20, 5, 30, 8, 20]
  >>> t
  (10, 20, 8, 38)
  >>> t[0]
  10
  >>> t[0] = 100   # 元组不可变，报错
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: 'tuple' object does not support item assignment
  ```

### 字典

- 字典是由键-值（key-value）对构成的映射数据类型

- 通过键取值，不支持下标操作

  ```bash
  >>> d1 = {"name": "tom", "age": 20}
  >>> len(d1)
  2
  >>> 'tom' in d1   # tom是字典的key吗
  False
  >>> 'name' in d1  # name是字典的key吗
  True
  >>> d1['name']    # 通过key取value
  'tom'
  ```

## 数据类型总结

### 按存储模型分类

- 标量：字符串、数字
- 容器：列表、元组、字典

### 按访问模型分类

- 直接：数字
- 顺序：字符串、列表、元组
- 映射：字典

### 按更新模型分类

- 不可变：数字、字符串、元组

- 可变：列表、字典

  ```bash
  >>> s1 = 'python'
  >>> l1 = [10, 20, 30]
  >>> s1[0]
  'p'
  >>> l1[0]
  10
  >>> l1[0] = 100
  >>> s1[0] = 'P'   # 字符串不可变，不能对它直接修改
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: 'str' object does not support item assignment
  >>> s1 = 'Python'  # 整体重新赋值
  
  >>> l1
  [100, 20, 30]
  >>> l2 = l1     # l1和l2指向内存的相同地址
  >>> l2
  [100, 20, 30]
  >>> l2[-1] = 300  # 修改l2也会影响到l1
  >>> l2
  [100, 20, 300]
  >>> l1
  [100, 20, 300]
  ```

思考题：

1. 有如下的数据结构：

```
users = [(1, 'tom'), (2, 'jerry'), (3, 'bob')]
```

如果只想取出jerry，该怎么办？

1. 有如下的数据结构

```
users = [{'name': 'nb', 'age': 20}, {'name': 'plj', 'age': 18}]
```

如果想取出nb和20，该怎么办？

