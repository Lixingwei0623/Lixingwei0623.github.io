@[TOC](python基础知识)

==前言：本文适合具备C、java等语言基础的python初学者==
# 一、python简介
## 1.优势与特点：
1. 代码开源；
2. 代码像自然语言一样易懂；
3. 适用于短周期开发的日常任务；
5. 代码优雅、简单、明确；
6. 代码量少；
7. 面向对象；
8. 有强大的标准库和第三方模块；
9. 可扩展性好，能很方便的调用其他语言；

## 2.开发环境
python的源程序是特殊格式的文本文件，所有的文本编辑器都可以直接编辑python代码，python是解释执行的，目前最常用的解释器是python2和python3。
在linux下运行python十分便捷，编写好后，中端直接输入python+filename即可。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109111436920.png)

也可以直接输入python，交互式的执行python语句。
![在这里插入图片描述](https://img-blog.csdnimg.cn/2021010911160666.png)
不过，最常用的IDE还是pycharm，之后的演示均转移到pycharm上。
![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109112022753.png)
# 二、python基本数据类型
Python 中的变量不需要声明。每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。变量的类型不会显示的声明

```
#注释：python中使用#来表示单行注释

num1=100    #整形变量
num2=100.0	#浮点型
numString="123"	#字符串
```

## 标准数据类型：

* Number（数字）
  * String（字符串）
  * List（列表）
  * Tuple（元组）
  * Set（集合）
  * Dictionary（字典）

### 1.Number（数字）
Python3 支持 int、float、bool、complex（复数）

	a, b, c, d = 20, 5.5, True, 4+3j

![在这里插入图片描述](https://img-blog.csdnimg.cn/20210109115524597.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzQzMjg5NzEx,size_16,color_FFFFFF,t_70)
数值运算：

	1+1    #加法	
	2.1-1    #减法
	2.1*2    #乘法
	2/4     #除法
	7//4    #整除，此结果为1
	7%4    #取余
	2**10    #n次方运算，此结果为1024

### String（字符串）
Python中的字符串用单引号 ' 或双引号 " 括起来，同时使用反斜杠 \ 转义特殊字符。

索引值以 0 为开始值，-1 为从末尾的开始位置。

	str="hellopython"
	print(str[0:4])
	print(str[1:-1])
	print(str[2:])
	print(str+"hellostring")
运行结果：

	hell
	ellopytho
	llopython
	hellopythonhellostring

### List（列表）
列表可以完成大多数集合类的数据结构实现。列表中元素的类型可以不相同，它支持数字，字符串甚至可以包含列表（所谓嵌套）。

列表是写在方括号 [] 之间、用逗号分隔开的元素列表。

和字符串一样，列表同样可以被索引和截取，列表被截取后返回一个包含所需元素的新列表。

	onelist = ["abc" , 12, 1.2 , True ]
	print(onelist[0:2])
	print(onelist[1:-1])
	print(onelist[2:])
	print(onelist + onelist[0:2])

运行结果如下

	['abc', 12]
	[12, 1.2]
	[1.2, True]
	['abc', 12, 1.2, True, 'abc', 12]

### Tuple（元组）
元组（tuple）与列表类似，不同之处在于元组的元素不能修改。元组写在小括号 () 里，元素之间用逗号隔开。

	tuple = ( 'abcd', 786 , 2.23, 'runoob', 70.2  )
	tinytuple = (123, 'runoob')
	
	print (tuple)             # 输出完整元组
	print (tuple[0])          # 输出元组的第一个元素
	print (tuple[1:3])        # 输出从第二个元素开始到第三个元素
	print (tuple[2:])         # 输出从第三个元素开始的所有元素
	print (tinytuple * 2)     # 输出两次元组
	print (tuple + tinytuple) # 连接元组

运行结果：

	('abcd', 786, 2.23, 'runoob', 70.2)
	abcd
	(786, 2.23)
	(2.23, 'runoob', 70.2)
	(123, 'runoob', 123, 'runoob')
	('abcd', 786, 2.23, 'runoob', 70.2, 123, 'runoob')

### Set（集合）
里面的元素不允许重复，重复元素会被自动删除
可以使用大括号 { } 或者 set() 函数创建集合

	a = {"csdn","zhihu","csdn"}
	b = {"baidu","tencent","csdn"}
	print(a)
	print(a-b)	#a集合减去a,b的交集
	print(a|b)	#a，b集合的并集
	print(a&b)	#a，b集合的交集
	print(a^b)	#a，b两集合中各自不同的元素组成的集合

运行结果如下：

	{'zhihu', 'csdn'}
	{'zhihu'}
	{'csdn', 'baidu', 'tencent', 'zhihu'}
	{'csdn'}
	{'baidu', 'zhihu', 'tencent'}

### Dictionary（字典）
字典是一种映射类型，字典用 { } 标识，它是一个无序的 键(key) : 值(value) 的集合。

	dict = {}	#空字典
	dict['one'] = "1 - CSDN"
	dict[2]     = "2 - csdn"
	
	tinydict = {'name': 'csdn','code':1, 'site': 'www.csdn.net'}
	
	print (dict['one'])       # 输出键为 'one' 的值
	print (dict[2])           # 输出键为 2 的值
	print (tinydict)          # 输出完整的字典
	print (tinydict.keys())   # 输出所有键
	print (tinydict.values()) # 输出所有值

运行结果：

	1 - CSDN
	2 - csdn
	{'name': 'csdn', 'code': 1, 'site': 'www.csdn.net'}
	dict_keys(['name', 'code', 'site'])
	dict_values(['csdn', 1, 'www.csdn.net'])

# 三、逻辑控制
## if语句

	if condition_1:
	    statement_block_1
	elif condition_2:
	    statement_block_2
	else:
	    statement_block_3

注意if后面不需要()来包裹条件，不需要{}来包裹语句，注意要加``:``，注意控制缩进来代替{}。

## while循环

	sum = 0
	counter = 1
	while counter <= 100:
	    sum = sum + counter
	    counter += 1

与C语言、java的while循环大同小异

## for循环
	#从容器中逐个取元素至x中，直至取完
	languages = ["C", "C++", "Perl", "Python"]
	for x in languages:
	    print (x)

### range()函数
for循环常与range()函数搭配使用，range()可以生成一个数字序列

	for i in range(5):
	    print(i)
	for i in range(5,9):
	    print(i)
	for i in range(0,10,3):
	    print(i)

生成的序列分别是：

	0,1,2,3,4
	5,6,7,8
	0,3,6,9

## break和continue语句
break 语句可以跳出 for 和 while 的循环体。如果你从 for 或 while 循环中终止，任何对应的循环 else 块将不执行。

continue 语句被用来告诉 Python 跳过当前循环块中的剩余语句，然后继续进行下一轮循环。

# 四、函数
函数是组织好的，可重复使用的，用来实现单一，或相关联功能的代码段。

自定义函数：

	def max(a,b):
		if a>b:
			return a
		else:
			return b

注意一定控制好缩进，缩进的对齐代替了其他语言的{}，另外函数结束一定有``return``语句，``return``后面不跟值表示没有返回值。

注意定义好函数后只有调用函数，函数代码才会执行，调用方式例如：``c=max(3.14,3.15)``

# 五、输入输出

	str = input("输入提示，例如请输入：")
	print(str)


# 六、类和对象

	class Student:
		def __init__(self,na):
			self.name=na
		name="zhangsan"
		def getName(self):
			return self.name

上面设计了一个Student类，其中``__init()__``是构造函数，``self``是创建对象是自身的引用，相当于java中的``this``,所有类的方法都需要包含该形参。
私有属性或方法只需以双下划线开头即可
如``__name``和``def __getName(self)``

## 类的实例化

	stu=Student("李四")

## 类的继承

在定义类时只需在``()``中写出需要继承的父类即可，可以继承多个父类，如：

	class Student(People):
		#类的属性方法等

	class A(B,C):
		#类的属性方法
