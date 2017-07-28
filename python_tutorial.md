
#  python 简明教程 
 改编自多个网上教程 by [hwdong](http://hwdong.com) 

## Python 简介
* python是一种*强类型(strongly typed 即数据都必具有某种类型)*、*动态类型(dynamically.即变量的类型可以变化) *、*隐类型(implicitly typed.不需要显式说明变量的类型)*、*case sensitive(大小写敏感. var和Var是不同名字)*、*object-oriented(面向对象. 即所有东西都是对象)*。

* python优点： 简单易学，编程效率高（其他语言几百行的代码工作，python往往仅需几行代码），除操作系统这类设计硬件的编程外，几乎可以胜任各种编程任务:网站开发、数据处理、科学计算、网络、图形图像、...。

* python缺点： 解释执行、速度慢，源代码无法加密。

 2017年python是在IEEE Spectrum排名第一的编程语言

![](http://img.mp.itc.cn/upload/20170720/3a884df6a6f84615b55447d56405fbb1_th.jpg)

## python安装

*在Windows上安装Python*: 下载[python2.7.13](https://www.python.org/downloads/windows/),注意勾选pip和将python加到系统路径中。安装完成后，在命令行输入python。如果出现如下界面，说明安装成功。

![](https://www.liaoxuefeng.com/files/attachments/0013868165417047ec57a2e466e4861a525d106e0b7e6b6000/0)

如出现如下错误： “‘python’不是内部或外部命令，也不是可运行的程序或批处理文件”。
说明python程序的目录（C:\Python27）没有在系统路径path下，需要手工添加就可以该路径到系统路径下，具体方法是：
假设python的安装路径为c:\python27，则在 “我的电脑”->属性->高级->环境变量->系统变量中的PATH中添加该目录即可。

## python两种编程模式

*  **交互式命令行**: 类似于Matlab等语言，在交互式环境的提示符>>>下，直接输入代码，按回车,立即得到相应的结果。如输入: 100+200 ，然后回车


```python
100+200
```




    300



如输入: print 'hello, world' ，然后回车


```python
print 'hello, world'
```

    hello, world
    

* **脚本文件模式**：将python的命令放在一个后缀是.py的文件如"hello.py"中，然后在命令行执行：python hello.py

编写脚本文件可以用任何文本或代码编辑工具，常用的文本工具有sublime和notepad++。如图所示：

![](https://www.liaoxuefeng.com/files/attachments/0013869285094083033fe5b249c4f90b6c32d98cd45f961000/0)

![](https://www.liaoxuefeng.com/files/attachments/001386928520603e4fd4153dbfb4027850cd7db6a380f53000/0)


以 .py结尾的文件称为**脚本(scipt)或模块(modules)**。模块构成了python各种各样的程序库。

## 变量(variable)和值(value)
python的每个对象（值）都可以用一个名字来标记，称为变量（名）(variable)。每个对象（值或数据）在内存里都占据一块内存，**变量记录了数据或值（value）的内存位置**。 如：


```python
a=3
b= 'hello'
myvar = 12.54
c=myvar+a
print(c)
a+2
```

    15.54
    




    5



变量a、b、myvar分别表示整数3、字符串'hello'、浮点型实数12.54。并用运算符'+'对其中的变量进行了加法运算。a、b、myvar变量定义时不需要说明其类型，可以根据其变量值隐含地确定其类型(**隐类型**)。

**数据的类型就决定了占用内存空间的大小，以及对这种类型数据能进行什么样的运算**，通常，同类型的才能运算，不同类型的不能进行相关的运算，除非不同类型的如果能从低的类型转化为高的类型,如整型转化为浮点型，如“myvar+a”中的'a'在加法运算时转化成了浮点型。下面代码则出错：


```python
a=3
b= 'hello'
a+b
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    <ipython-input-13-abbad45f1aa6> in <module>()
          1 a=3
          2 b= 'hello'
    ----> 3 a+b
    

    TypeError: unsupported operand type(s) for +: 'int' and 'str'



```python
a= 3
b=a
a="hello"
print a,b
```

    hello 3
    

## 标准数据类型 Standard Data Types
python有6种标准数据类型：Numbers（数值）、String（串）、List（列表）、Tuple（元祖）、Dictionary（字典）、Set（集合）。 Numbers（数值类型）又分为：int (signed integers)（整型/有符号整型）、long（长整型）、float（浮点实数类型）、complex（复数类型）。int和long都表示整数，后者占据的位数更多，可以表示更大的整数。如：
```
-786   ## int类型 
-0490  ## 八进制int类型
-0x260 ## 十六进制int类型

51924361L ## 后缀跟L表示long类型
-0x19323L ## 后缀跟L的 十六进制long类型
15.20      ## float浮点类型 
32.3+e18      ## 科学计数法float浮点类型 

.876j   ## complex（复数类型） 
4.53e-7j   ## complex（复数类型）
```

## help、dir、__doc__

  可以通过**help**命令查询一个对象的信息,通过**dir**查询对象的方法有哪些，通过**_doc__** 访问对象的文档说明。
  
  也可以用**?**代替**help**,或用**??**获得对象的源代码。



```python
help(abs)
```

    Help on built-in function abs in module __builtin__:
    
    abs(...)
        abs(number) -> number
        
        Return the absolute value of the argument.
    
    


```python
dir(abs)
```




    ['__call__',
     '__class__',
     '__cmp__',
     '__delattr__',
     '__doc__',
     '__eq__',
     '__format__',
     '__ge__',
     '__getattribute__',
     '__gt__',
     '__hash__',
     '__init__',
     '__le__',
     '__lt__',
     '__module__',
     '__name__',
     '__ne__',
     '__new__',
     '__reduce__',
     '__reduce_ex__',
     '__repr__',
     '__self__',
     '__setattr__',
     '__sizeof__',
     '__str__',
     '__subclasshook__']




```python
abs.__doc__
```




    'abs(number) -> number\n\nReturn the absolute value of the argument.'




```python
abs?
```

Docstring:
abs(number) -> number

Return the absolute value of the argument.
Type:      builtin_function_or_method

## 动态类型
变量a,b相继表示整数3，随后变量a被修改用于表述字符串"hello"，而b仍然表示整数3。我们看到变量a的类型从整型变成了浮点型。即变量类型根据其表示值的类型的变换而变化。

## 字符串 (string)

可以用单引号'或双引号"来表述单行字符串，并且一种引号的字符串可以包括另外一种的引号。而多行字符串需要用三引号'''。如：


```python
print "He said 'hello'."
var = '''hello:
     This is a 
    multile string '''
print var
```

    He said 'hello'.
    hello:
         This is a 
        multile string 
    


```python
str = 'Hello World!'

print str          # 打印整个字符串
print str[0]       # str[0]表示字符串的第一个字符，下标从0开始算起，不同于Matlab等语言下标从1开始
print str[2:5]     # str[2:5]表示第3到底6个字符之间的子串，不包括第6个字符
print str[2:]      # str[2:] 表示从第3个字符开始的子串
print str * 2      # 乘法符号*用于复制多个同样字符串
print str + "TEST" # 拼接2个字符串
```

    Hello World!
    H
    llo
    llo World!
    Hello World!Hello World!
    Hello World!TEST
    

**格式化**


```python
'Hello, %s' % 'world'
```




    'Hello, world'




```python
a= 'hello'
b = "world"
print("a : %s and b : %s" % (a,b))
```

    a : hello and b : world
    


```python
'Hi, %s, you have $%d.' % ('Michael', 1000000)
```




    'Hi, Michael, you have $1000000.'



在字符串内部，%s表示用字符串替换，%d表示用整数替换，在字符串外部也要以%开始。有几个%?占位符，后面就跟几个变量或者值，顺序要对应好。如果只有一个%?，括号可以省略。

**Unicode串**

普通的字符串'ABC'在Python内部都是ASCII编码的，即每个字符占用一个字节，但这种表示法只能表示255个字符，没法表示成千上万的非字母语言字符如中文等。

Unicode串，以u开头，u'中文'表示。也可以用\u后面跟十六进制的Unicode码来表示Unicode串，如：u'中'和u'\u4e2d'是一样的；u'A'和u'\u0041'也是一样的。


```python
print u'中'
print '\u4e2d'
```

**UTF-8编码**

UTF-8编码用可变字节数来表示字符，对于ASCII编码,等于其UTF-8编码,而Unicode编码和UTF-8编码可以相互转化。

把u'xxx'转换为UTF-8编码的'xxx'用encode('utf-8')方法：
```python
 u'ABC'.encode('utf-8')
```
把UTF-8编码表示的字符串'xxx'转换为Unicode字符串u'xxx'用decode('utf-8')方法
```python
 'abc'.decode('utf-8')
```

由于Python源代码也是一个文本文件，所以，当你的源代码中包含中文的时候，在**保存源代码时，就需要务必指定保存为UTF-8编码**。当Python解释器读取源代码时，为了让它按UTF-8编码读取，我们通常在文件开头写上这两行：
```python
#!/usr/bin/env python
# -*- coding: utf-8 -*-
```
第一行注释是为了告诉Linux/OS X系统，这是一个Python可执行程序，Windows系统会忽略这个注释；

第二行注释是为了告诉Python解释器，按照UTF-8编码读取源代码，否则，你在源代码中写的中文输出可能会有乱码。

## 标识符和关键字
python中的变量名、函数名、类名等都是由字母、数字等构成的**标识符**。python规定标识符必须是26个大小写的英文字母和下划线(_)开头的，后面可跟一系列的字母、数字、下划线。 标识符中不允许出现其他特殊字符如： @, $, and % 等。

有一些标识符因为被python语言本身占用了，称为**关键字**,如print。自定义的标识符不能和这些关键字相同.关键字有：

and	exec	not assert	finally	or break	for	pass class	from	print continue	global	raise
def	if	return del	import	try elif	in	while else	is	with except	lambda	yield

## 容器类型 lists（列表）, tuples(元素) 、dictionaries（字典）、sets（集合）

* list（列表）是一维数组（但可以定义列表的列表，即一个列表元素本身也是一个列表）。用左右方括号[和]包围.

* tuple（元素）是**不可修改的（immutable）**一维数组。用左右方括号(和)包围.

* set（集合）是不同元素的无序集合，元素之间没有任何特别的关系。用左右方括号{和}包围.

* dictionary（字典）是通常数据结构的所谓“**哈希表(Hash Table)**”或**关键数组( associative arrays)**,是一种<键、值>(<key,value>)的集合.用左右方括号{和}包围.其中每个元素的ley和value之间用分号隔开。

如：


```python
mylist = ["List item 1", 2, 3.14]  # 定义一个列表list
print mylist
mylist[0] = "List item 1 again"    # 修改列表的第一个元素
mylist[-1] = 3.21                  # 修改列表的最后一个元素, -1下标指向最后一个元素
print mylist

mydict = {"Key 1": "Value 1", 2: 3, "pi": 3.14}  # 定义一个字典dictionary
print mydict
mydict["pi"] = 3.15         # 修改关键字key="pi"的对应元素的值(value)
print mydict

mytuple = ("Tuple item 1", 2, 3.14)  # 定义一个列表元素
print mytuple,mytuple[1]             ## 打印整个元组和元祖的死一个元素

mix_collect = [1, ["another", "list"], ("a", "tuple")]  ## 列表元素本身可能也是一个列表或元祖
print mix_collect
```

    ['List item 1', 2, 3.14]
    ['List item 1 again', 2, 3.21]
    {'Key 1': 'Value 1', 2: 3, 'pi': 3.14}
    {'Key 1': 'Value 1', 2: 3, 'pi': 3.15}
    ('Tuple item 1', 2, 3.14) 2
    [1, ['another', 'list'], ('a', 'tuple')]
    

列表(list)和元组(tuple)都可以类似其他语言的数组一样用下标去访问其中的元素,注意：-1下标表示最后一个元素，类似的，-2、-3表示倒数第二个、第三个。和列表(list)、dictionary（字典）、set（集合）不同，元组(tuple)不能被修改。

**列表切片(List Slices)**: 


```python
list = ['a', 'b', 'c', 'd']
print(list[:])     ## 冒号:表示左右下标范围
print list[1:-1]   ## ['b', 'c']  第2个元素（下标1）和最后一个算法（下标-1）之间的范围，不包括-1.
list[0:2] = 'z'    ## replace ['a', 'b'] with ['z']
print list         ## ['z', 'c', 'd']
list = ['a', 'b', 'c', 'd','e','f']
print(list[::2])   ## 从0开始，间隔2，一直到最后
```

    ['a', 'b', 'c', 'd']
    ['b', 'c']
    ['z', 'c', 'd']
    ['a', 'c', 'e']
    


```python
mytuple = ("List item 1", 2, 3.14)        ## 定义一个列表list
mytuple[0] = "we can't modify tuple"      ## 不能修改元组
```

可以用内在函数**range**产生一个列表(list). 其中range(n) 产生数字0, 1, ... n-1的列表，而 range(a, b) 返回数字 a, a+1, ... b-1构成的列表。


```python
range(5)
```




    [0, 1, 2, 3, 4]




```python
a= -3
b = 9
range(a,b)
```




    [-3, -2, -1, 0, 1, 2, 3, 4, 5, 6, 7, 8]



我们可以通过dir(list)了解列表(list)有[哪些方法](https://developers.google.com/edu/python/lists)，用于对列表进行操作。其方法有：
```
'append',
 'count',
 'extend',
 'index',
 'insert',
 'pop',
 'remove',
 'reverse',
 'sort']
```
比如：


```python
list = ['larry', 'curly', 'moe']
list.append('shemp')         ## append elem at end
list.insert(0, 'xxx')        ## insert elem at index 0
list.extend(['yyy', 'zzz'])  ## add list of elems at end
print list  ## ['xxx', 'larry', 'curly', 'moe', 'shemp', 'yyy', 'zzz']
print list.index('curly')    ## 2

list.remove('curly')         ## search and remove that element
list.pop(1)                  ## removes and returns 'larry'
print list  ## ['xxx', 'moe', 'shemp', 'yyy', 'zzz']
```

    ['xxx', 'larry', 'curly', 'moe', 'shemp', 'yyy', 'zzz']
    2
    ['xxx', 'moe', 'shemp', 'yyy', 'zzz']
    

**集合(set)示例：**


```python
animals = {'cat', 'dog'}
print('cat' in animals)   # Check if an element is in a set; prints "True"
print('fish' in animals)  # prints "False"
animals.add('fish')       # Add an element to a set
print('fish' in animals)  # Prints "True"
animals.add('cat')        # Adding an element that is already in the set does nothing
print(len(animals))       # Prints "3"
animals.remove('cat')     # Remove an element from a set
print(len(animals))       # Prints "2"
```

    True
    False
    True
    3
    2
    

## 控制语句（Flow control statements）

条件语句用**if**定义, 循环语句用**for**和 **while**定义。

**if 条件语句** 有下列几种形式:  

```python
     if 条件
         程序块
```
 或 
```python
     if 条件1
         程序块1
     else 条件2
         程序块2
```
 或 
```python
     if 条件1
         程序块1
     elif 条件2
         程序块2
     elif 条件3
         程序块3
     else 条件4
         程序块4
```    
例如：


```python
var = 100
if ( var  == 100 ) : 
    print "Value of expression is 100"
print "Good bye!"

```

    Value of expression is 100
    Good bye!
    

**注意**： 第一个print必须缩进几个空格，表示这个print语句是属于if程序块的。再注意下面的每个print的缩进：


```python
age = 3
if age >= 18:
    print 'adult'
elif age >= 6:
    print 'teenager'
else:
    print 'kid'
```

    kid
    

**for 语句**形式:  

```python
for e in 某容器:
   程序块
```
如：
```python
animals = ['cat', 'dog', 'monkey']
for animal in animals:
    print(animal)
# Prints "cat", "dog", "monkey", each on its own line.
```

如果想得到每个元素在容器如list中的索引，可以采用下列for语句，其中idx是元素e在容器中的下标：

```python
for idx e in 某容器:
   程序块
```
如：
```python
animals = ['cat', 'dog', 'monkey']
for idx, animal in enumerate(animals):
    print('#%d: %s' % (idx + 1, animal))
# Prints "#1: cat", "#2: dog", "#3: monkey", each on its own line
```


```python
rangelist = range(10)
print(rangelist)
for number in rangelist: 
    if number >7:        
        break
    elif number%2==0:  ## % 是取模运算
        continue;
    else:       
        print number

for
```

    [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    1
    3
    5
    7
    

**while语句**形式: 类似于if语句，但只要条件为真，就一直执行while程序块中的代码。
```python
while 条件
    程序块
```


```python
sum = 0
n = 99
while n > 0:
    sum = sum + n
    n = n - 2
print sum
```

    2500
    

**猜数字游戏** ： 程序随机生成介于1和100之间的一个整数，让用户从键盘尝试猜测这个数字，超过一定猜测次数就失败。

random.randint(1,100) 用于生成随机整数，input函数用于接收键盘输入


```python
#!/usr/bin/env python
import random
secret=random.randint(1,100)
guess=0
tries=0
print "This game is to guess a number for you!"
print " It is a number form 1 to 99,I'll give you 6 times to try. "
while guess != secret and tries < 6:
    guess=input("Please input your guess number: ")
    if guess < secret:
        print "====Your guess is too low !====\n"
                                                                                                                                                                
    elif guess > secret:
        print "====Your guess is too high!====\n"
    tries=tries+1
if guess == secret:
        print "Congratulations to you! Your  guess is right ! "
else:
        print "No more guesses! Better luck next time for you!"
        print "The secret number was",secret
```

    This game is to guess a number for you!
     It is a number form 1 to 99,I'll give you 6 times to try. 
    

## comprehensions

**List comprehensions**

下列求平方和代码


```python
nums = [0, 1, 2, 3, 4]
squares = []
for x in nums:
    squares.append(x ** 2)
print(squares)   # Prints [0, 1, 4, 9, 16]
```

    [0, 1, 4, 9, 16]
    

可以用List comprehensions简化为：


```python
nums = [0, 1, 2, 3, 4]
squares = [x ** 2 for x in nums]
print(squares)   # Prints [0, 1, 4, 9, 16
```

List comprehensions也可以带条件语句conditions或with


```python
nums = [0, 1, 2, 3, 4]
even_squares = [x ** 2 for x in nums if x % 2 == 0]
print(even_squares)  # Prints "[0, 4, 16]"
```

    [0, 4, 16]
    

再如：


```python
[m + n for m in 'ABC' for n in 'XYZ']
## ['AX', 'AY', 'AZ', 'BX', 'BY', 'BZ', 'CX', 'CY', 'CZ']
```




    ['y=B', 'x=A', 'z=C']



列出当前目录下的所有文件和目录名，可以通过一行代码实现：


```python
import os # 导入os模块，模块的概念后面讲到
[d for d in os.listdir('.')] # os.listdir可以列出文件和目录
```




    ['.ipynb_checkpoints', 'hello.py', 'python_tutorial.ipynb', 'readme.md']



**Dictionary comprehensions**


```python
d = {'x': 'A', 'y': 'B', 'z': 'C' }
[k + '=' + v for k, v in d.iteritems()]
##  ['y=B', 'x=A', 'z=C']
```




    ['y=B', 'x=A', 'z=C']




```python
d = {(x, x + 1): x for x in range(10)}  # Create a dictionary with tuple keys
t = (5, 6)        # Create a tuple
print(type(t))    # Prints "<class 'tuple'>"
print(d[t])       # Prints "5"
print(d[(1, 2)])  # Prints "1"
```

    <type 'tuple'>
    5
    1
    

**Set comprehensions:**


```python
from math import sqrt
nums = {int(sqrt(x)) for x in range(30)}
print(nums)  # Prints "{0, 1, 2, 3, 4, 5}"
```

    set([0, 1, 2, 3, 4, 5])
    

##  一些语法点小结

* '#'开头的是**程序注释**，不是程序代码，不会被执行。

* 连续的同样缩进(Indentation)的语句属于同一个程序块。称为**一致缩进(Indentation)**。比如whilie语句的2个语句必须对齐（缩进同样个数的空格）。下列写法
```python
  while n > 0:
      sum = sum + n
     n = n - 2
```
将导致语法错误

* 多行语句Multi-Line Statements: 用连续\符号表示一条语句的多行连续
```
total = item_one + \
        item_two + \
        item_three
```
* 同一行的多行语句： 多个写在同一行的语句可以用分号;隔开
```
import sys; x = 'foo'; sys.stdout.write(x + '\n')
```
* 不同类型数据能进行的运算操作是不一样的。和其他语言一样，常见的运算有：算术运算、逻辑运算、比较运算、移位运算等。参见链接:[https://www.tutorialspoint.com/python/python_basic_operators.htm](https://www.tutorialspoint.com/python/python_basic_operators.htm)

## 用户定义函数（User-defined Functions）

 关键字 **def** 用于定义一个函数.如下面定义了一个叫做hello的函数，带有参数name和loud，其中第二个参数loud具有默认值，叫默认参数。


```python
def hello(name, loud=False):
    if loud:                                       ## 如果  loud真，执行下面的print
        print('HELLO, %s!' % name.upper())
    else:                                          ## 否则 ,loud为假，执行下面的print
        print('Hello, %s' % name)

hello('Bob') # Prints "Hello, Bob"
hello('Fred', loud=True)  # Prints "HELLO, FRED!"
```

    Hello, Bob
    HELLO, FRED!
    

再看一个例子：


```python
#!/usr/bin/env python

# import modules used here -- sys is a very standard one
import sys

# Gather our code in a main() function
def main():
    print 'Hello'
    print 'sys.argv[0]', sys.argv[0]
    print 'sys.argv[1]', sys.argv[1]
    # Command line args are in sys.argv[1], sys.argv[2] ...
    # sys.argv[0] is the script name itself and can be ignored

# Standard boilerplate to call the main() function to begin
# the program.
if __name__ == '__main__':
    main()
```

在命令行运行该脚本(scipt):
```
$ python hello.py Guido
```
Hello 
sys.argv[0] hello.py
sys.argv[1] Guido

*注意：* 
   * 关键字 **def** 用于定义一个函数
   * 关键字 **if** 用于判断条件是否成立
   * main函数中的3个并列语句属于同一个代码块(block),python要求同一个代码块中的并列语句必须**一致缩进(Indentation)**（即：所有行前面必须有同行的空格数目。）。如果不**一致缩进**，就会报错。如：


```python
 print 'hello'
    print 'world'
```


      File "<ipython-input-2-f8be96646c4f>", line 2
        print 'world'
        ^
    IndentationError: unexpected indent
    


   例如上面程序中的“if __name__ == '__main__':”当判断条件“ __name__ == '__main__'”成立时就执行main函数。对于一个脚本文件，其中的内在变量（built-in variable）__name__等于该模块名字，但如果该脚本文件是作为主程序文件执行时，__name__将被设置成字符串"__main__"。
  [例如]()，假设有2个脚本文件如下：
  
```python
  # file one.py
def func():
    print("func() in one.py")

print("top-level in one.py")

if __name__ == "__main__":
    print("one.py is being run directly")
else:
    print("one.py is being imported into another module")
    
    
# file two.py
import one

print("top-level in two.py")
one.func()

if __name__ == "__main__":
    print("two.py is being run directly")
else:
    print("two.py is being imported into another module")
```

假如我们执行
```python
python one.py
```
其结果是：
```python
top-level in one.py
one.py is being run directly
```

假如我们执行
```python
python two.py
```
其结果是：
```python
top-level in one.py
one.py is being imported into another module
top-level in two.py
func() in one.py
two.py is being run directly
```

**lambda函数**：也称为**匿名函数**。只能有一个表达式，不用写return，返回值就是该表达式的结果。

用匿名函数有个好处，因为函数没有名字，不必担心函数名冲突。此外，匿名函数也是一个函数对象，也可以把匿名函数赋值给一个变量，再利用变量来调用该函数：


```python
funcvar = lambda x: x + 1
print(funcvar(1))

map(lambda x: x * x, [1, 2, 3, 4, 5, 6, 7, 8, 9])
[1, 4, 9, 16, 25, 36, 49, 64, 81]
```

    2
    




    [1, 4, 9, 16, 25, 36, 49, 64, 81]



**递归函数**：调用自身的函数。和其他编程语言一样。


```python
def fact(n):
    if n==1:  ## 如果n等于1，就直接返回值1
        return 1
    return n * fact(n - 1)
fact(5)
```




    120



fact(5)的计算过程
```python
===> fact(5)
===> 5 * fact(4)
===> 5 * (4 * fact(3))
===> 5 * (4 * (3 * fact(2)))
===> 5 * (4 * (3 * (2 * fact(1))))
===> 5 * (4 * (3 * (2 * 1)))
===> 5 * (4 * (3 * 2))
===> 5 * (4 * 6)
===> 5 * 24
===> 120
```

**快速排序**：[原理](https://zh.wikipedia.org/wiki/%E5%BF%AB%E9%80%9F%E6%8E%92%E5%BA%8F)可以网上搜索。


```python
def quicksort(arr):
    if len(arr) <= 1:                          ## 如果 输入序列长度小于等于1，直接返回
        return arr
    pivot = arr[len(arr) // 2]                  ##任意选择一个如中间元素作为基准元素，将原序列一分为二
    left = [x for x in arr if x < pivot]        ## left是小于基准元素组成的子序列
    middle = [x for x in arr if x == pivot]     ## middle是等于基准元素组成的子序列
    right = [x for x in arr if x > pivot]       ##  right是大于基准元素组成的子序列
    return quicksort(left) + middle + quicksort(right)  ##对left、right重复上述过程

print(quicksort([3,6,8,10,1,2,1]))
# Prints "[1, 1, 2, 3, 6, 8, 10]"
```

    [1, 1, 2, 3, 6, 8, 10]
    

## 类Classes
python支持有限形式的多继承(multiple inheritance )。私有变量名和方法名前通常有2个下划线。类中的“__init__”是初始化构造函数。



```python
class Greeter(object):

    # Constructor
    def __init__(self, name):
        self.name = name  # Create an instance variable

    # Instance method
    def greet(self, loud=False):
        if loud:
            print('HELLO, %s!' % self.name.upper())
        else:
            print('Hello, %s' % self.name)

g = Greeter('Fred')  # Construct an instance of the Greeter class
g.greet()            # Call an instance method; prints "Hello, Fred"
g.greet(loud=True)   # Call an instance method; prints "HELLO, FRED!"
```

    Hello, Fred
    HELLO, FRED!
    

## Exceptions
** try-except [exceptionname]**程序块：try 中程序块是正常代码，而**except**则是处理名叫“**exceptionname**”某种异常，未被except处理的异常，则统一由finally块处理。


```python
def some_function():
    try:
        # Division by zero raises an exception
        10 / 0
    except ZeroDivisionError:  ## 除以0的错误
        print("Oops, invalid.")
    else:
        # Exception didn't occur, we're good.
        pass
    finally:
        # This is executed after the code block is run
        # and all exceptions have been handled, even
        # if a new exception is raised while handling.
        print("We're done with that.")

some_function()
```

    Oops, invalid.
    We're done with that.
    


```python

```
