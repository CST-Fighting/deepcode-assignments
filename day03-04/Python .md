## Python

#### 变量类型

变量可以指定不同的数据类型，这些变量可以存储整数，小数或字符。

##### 变量赋值

Python 中的变量赋值不需要类型声明。

每个变量在内存中创建，都包括变量的标识，名称和数据这些信息。

每个变量在使用前都必须赋值，变量赋值以后该变量才会被创建。

等号 **=** 用来给变量赋值。

等号 **=** 运算符左边是一个变量名，等号 **=** 运算符右边是存储在变量中的值。例如：

##### 多个变量赋值

Python允许你同时为多个变量赋值。

```
a = b = c = 1;
```

也可以为多个对象指定多个变量:

```
a,b,c =1,2,3        #a=1,b=2,c=3
```

### 标准数据类型

在内存中存储的数据可以有多种类型。

例如，一个人的年龄可以用数字来存储，他的名字可以用字符来存储。

Python 定义了一些标准类型，用于存储各种类型的数据。

Python有五个标准的数据类型：

- Numbers（数字）
- String（字符串）
- List（列表）
- Tuple（元组）
- Dictionary（字典）

####  数字（Number）

数字数据类型用于存储数值。

他们是不可改变的数据类型，这意味着改变数字数据类型会分配一个新的对象。

当你指定一个值时，Number 对象就会被创建：

```
var1 = 1
var2 = 10
```

也可以使用del语句删除一些对象的引用。del语句的语法是：

```
del var1[,var2[,var3[,..,varN]]]
```

也可以通过使用del语句删除单个或多个对象的引用。例如：

```
del var
del var_a,var_b
```

Python支持四种不同的数字类型：

- int（有符号整型）
- long（长整型，也可以代表八进制和十六进制）
- float（浮点型）
- complex（复数）

```
int	      long	               float    	complex
10	  51924361L	                0.0	         3.14j
100	  -0x19323L                15.20	      45.j
-786	0122L	               -21.9	   9.322e-36j
080	0xDEFABCECBDAECBFBAEl     32.3e+18	     .876j
-0490	535633629843L	        -90.	    -.6545+0J
-0x260	-052318172735L   	  -32.54e100	   3e+26J
0x69	-4721885298529L	       70.2E-12  	4.53e-7j
```

- 长整型也可以使用小写 l，但是还是建议您使用大写 L，避免与数字 1 混淆。Python使用 L 来显示长整型。
- Python 还支持复数，复数由实数部分和虚数部分构成，可以用 a + bj,或者 complex(a,b) 表示， 复数的实部 a 和虚部 b 都是浮点型。

#### 字符串

字符串或串(String)是由数字、字母、下划线组成的一串字符。

一般记为 :

```
s = "a1a2...an"   #n>0
```

python的字串列表有2种取值顺序:

- 从左到右索引默认0开始的，最大范围是字符串长度少1

- 从右到左索引默认-1开始的，最大范围是字符串开头

  ```
  R  U  N  O  O  B
  0  1  2  3  4  5   #从左到右
  -6 -5 -4 -3 -2 -1   #从右到左
  ```

如果你要实现从字符串中获取一段子字符串的话，可以使用 **[头下标:尾下标]** 来截取相应的字符串，其中下标是从 0 开始算起，可以是正数或负数，下标可以为空表示取到头或尾。

**[头下标:尾下标]** 获取的子字符串包含头下标的字符，但不包含尾下标的字符。例如：

```
s = 'qwertyuiop'
print s[0:5];

#输出：qwert
```

当使用以冒号分隔的字符串，python 返回一个新的对象，结果包含了以这对偏移标识的连续的内容，左边的开始是包含了下边界。

上面的结果包含了 **s[1]** 的值 w，而取到的最大范围不包括**尾下标**，就是 **s[5]** 的值 t。

加号（+）是字符串连接运算符，星号（*）是重复操作。

```
str = 'Hello World!'
 
print str           # 输出完整字符串
print str[0]        # 输出字符串中的第一个字符
print str[2:5]      # 输出字符串中第三个至第六个之间的字符串
print str[2:]       # 输出从第三个字符开始的字符串
print str * 2       # 输出字符串两次
print str + "TEST"  # 输出连接的字符串
```

Python 列表截取可以接收第三个参数，参数作用是截取的步长，以下实例在索引 1 到索引 4 的位置并设置为步长为 2（间隔一个位置）来截取字符串：

```
letters = ['a','b','c','d','e']
print letters[1:4:1];
#输出：
['b', 'c', 'd']
```

```
letters = ['a','b','c','d','e']
print letters[1:4:2];
#输出：
['b', 'd']
```

####  转义字符

```
转义字符	              描述
\(在行尾时)	             续行符
\\	                   反斜杠符号
\'	                     单引号
\"	                     双引号
\a	                      响铃
\b	                 退格(Backspace)
\e	                      转义
\000	                   空
\n	                      换行
\v	                    纵向制表符
\t	                    横向制表符
\r	                      回车
\f	                      换页
\oyy	八进制数，y 代表 0~7 的字符，例如：\012 代表换行。
\xyy	十六进制数，以 \x 开头，yy代表的字符，例如：\x0a代表换行
\other	其它的字符以普通格式输出
```

##### 字符串运算符

下表实例变量 a 值为字符串 "Hello"，b 变量值为 "Python"：

```

操作符 	      描述	                                              实例
+	          字符串连接	                                              >>>a + b
                                                                   'HelloPython'
*	          重复输出字符串	                                        >>>a * 2
                                                                    'HelloHello'
[]	        通过索引获取字符串中字符	                                  >>>a[1]
                                                                       'e'
[ : ]	      截取字符串中的一部分	                                   >>>a[1:4]
                                                                     'ell'
in	成员运算符 - 如果字符串中包含给定的字符返回 True	                     >>>"H" in a
                                                                      True
not in	成员运算符 - 如果字符串中不包含给定的字符返回 True	                >>>"M" not in a
                                                                      True
r/R	    原始字符串 - 原始字符串：所有的字符串都是直接按照字面的意思来使用，      >>>print r'\n'
        没有转义特殊或不能打印的字符。 原始字符串除在字符串的第一个引号前         \n
        加上字母"r"（可以大小写）以外，与普通字符串有着几乎完全相同的语法。	     >>>print'R\n'
                                                                       \n
%	    格式字符串
```

#####  字符串格式化

Python 支持格式化字符串的输出 。尽管这样可能会用到非常复杂的表达式，但最基本的用法是将一个值插入到一个有字符串格式符 %s 的字符串中。

```
     符号          描述
      %c	 格式化字符及其ASCII码
      %s	 格式化字符串
      %d	 格式化整数
      %u	 格式化无符号整型
      %o	 格式化无符号八进制数
      %x	 格式化无符号十六进制数
      %X	 格式化无符号十六进制数（大写）
      %f	 格式化浮点数字，可指定小数点后的精度
      %e	 用科学计数法格式化浮点数
      %E	 作用同%e，用科学计数法格式化浮点数
      %g	 %f和%e的简写
      %G	 %F 和 %E 的简写
      %p	 用十六进制数格式化变量的地址
```

```
print "My name is %s and weight is %d kg!" % ('Zara', 21) 

#输出：
My name is Zara and weight is 21 kg!
```

```
符号	   功能
*	 定义宽度或者小数点精度
-	 用做左对齐
+	 在正数前面显示加号( + )
<sp> 在正数前面显示空格
#	 在八进制数前面显示零('0')，在十六进制前面显示'0x'或者'0X'(取决于用的是'x'还是'X')
0	 显示的数字前面填充'0'而不是默认的空格
%	 '%%'输出一个单一的'%'
(var)	映射变量(字典参数)
m.n.	m 是显示的最小总宽度,n 是小数点后的位数(如果可用的话)
```

##### 三引号

Python 中三引号可以将复杂的字符串进行赋值。

Python 三引号允许一个字符串跨多行，字符串中可以包含换行符、制表符以及其他特殊字符。

三引号的语法是一对连续的单引号或者双引号（通常都是成对的用）。

```
>>> hi = '''hi 
there'''
>>> hi   # repr()
'hi\nthere'
>>> print hi  # str()
hi 
there  
```

##### Unicode 字符串

Python 中定义一个 Unicode 字符串和定义一个普通字符串一样简单.



##### 字符串内建函数

字符串方法实现了string模块的大部分方法，如下表所示列出了目前字符串内建支持的方法，所有的方法都包含了对Unicode的支持，有一些甚至是专门用于Unicode的。

```
方法	描述
string.capitalize()                               把字符串的第一个字符大写
string.center(width)                              返回一个原字符串居中,并使用空格填充至长度 width 的新字符串
string.count(str, beg=0, end=len(string))         返回 str 在 string 里面出现的次数，如果 beg 或者 end 指定则返回指                                                   定范围内 str 出现的次数

string.decode(encoding='UTF-8', errors='strict')  以 encoding 指定的编码格式解码 string，如果出错默认报一个                                                           ValueError 的 异 常 ， 除非 errors 指 定 的 是 'ignore' 或                                                       者'replace'

string.encode(encoding='UTF-8', errors='strict')  以 encoding 指定的编码格式编码 string，如果出错默认报一个                                                           ValueError 的异常，除非 errors 指定的是'ignore'或者'replace'

string.endswith(obj, beg=0, end=len(string))      检查字符串是否以 obj 结束，如果beg 或者 end 指定则检查指定的范围内                                                   是否以 obj 结束，如果是，返回 True,否则返回 False.

string.expandtabs(tabsize=8)                      把字符串 string 中的 tab 符号转为空格，tab 符号默认的空格数是 8。


string.find(str, beg=0, end=len(string))          检测 str 是否包含在 string 中，如果 beg 和 end 指定范围，则检查是                                                   否包含在指定范围内，如果是返回开始的索引值，否则返回-1
string.format()                                   格式化字符串

string.index(str, beg=0, end=len(string))         跟find()方法一样，只不过如果str不在 string中会报一个异常.
string.isalnum()                                  如果 string 至少有一个字符并且所有字符都是字母或数字则返回True,否则                                                   返回False

string.isalpha()                                  如果 string 至少有一个字符并且所有字符都是字母则返回 True,
                                                  否则返回 False
string.isdecimal()                                如果 string 只包含十进制数字则返回 True 否则返回 False.
string.isdigit()                                  如果 string 只包含数字则返回 True 否则返回 False.
string.islower()                                  如果 string 中包含至少一个区分大小写的字符，并且所有这些(区分大小写                                                   的)字符都是小写，则返回 True，否则返回 False

string.isnumeric()                                如果 string 中只包含数字字符，则返回 True，否则返回 False
string.isspace()                                  如果 string 中只包含空格，则返回 True，否则返回 False.
string.istitle()                                  如果 string 是标题化的(见 title())则返回 True，否则返回 False
string.isupper()                                  如果 string 中包含至少一个区分大小写的字符，并且所有这些(区分大小写                                                   的)字符都是大写，则返回 True，否则返回 False
string.join(seq)                                  以 string 作为分隔符，将 seq 中所有的元素(的字符串表示)合并为一个新                                                   的字符串
string.ljust(width)                               返回一个原字符串左对齐,并使用空格填充至长度 width 的新字符串
string.lower()                                    转换 string 中所有大写字符为小写.
string.lstrip()                                   截掉 string 左边的空格
string.maketrans(intab, outtab])
maketrans()                                       方法用于创建字符映射的转换表，对于接受两个参数的最简单的调用方式，第一                                                 个参数是字符串，表示需要转换的字符，第二个参数也是字符串表示转换的目标。
max(str)                                          返回字符串 str 中最大的字母。
min(str)                                          返回字符串 str 中最小的字母。
string.partition(str)                             有点像 find()和 split()的结合体,从 str 出现的第一个位置起,把 字                                                     符串 string 分 成 一 个 3 元 素 的 元 组                                                                         (string_pre_str,str,string_post_str),如果 string 中不包含str                                                    则 string_pre_str == string.
string.replace(str1, str2,  num=string.count(str1)) 把 string 中的 str1 替换成 str2,如果 num 指定，则替换不超过                                                       num 次.
string.rfind(str, beg=0,end=len(string) )          类似于 find() 函数，返回字符串最后一次出现的位置，如果没有匹配项则                                                    返回 -1。
string.rindex( str, beg=0,end=len(string))         类似于 index()，不过是返回最后一个匹配到的子字符串的索引号。
string.rjust(width)                                返回一个原字符串右对齐,并使用空格填充至长度 width 的新字符串
string.rpartition(str)                             类似于 partition()函数,不过是从右边开始查找
string.rstrip()                                    删除 string 字符串末尾的空格.
string.split(str="", num=string.count(str))        以 str 为分隔符切片 string，如果 num 有指定值，则仅分隔 num+1 个                                                    子字符串
string.splitlines([keepends])                      按照行('\r', '\r\n', \n')分隔，返回一个包含各行作为元素的列表，如                                                    果参数 keepends 为 False，不包含换行符，如果为 True，则保留换行                                                    符。
string.startswith(obj, beg=0,end=len(string))      检查字符串是否是以 obj 开头，是则返回 True，否则返回 False。如果                                                    beg 和 end 指定值，则在指定范围内检查.
string.strip([obj])                                在 string 上执行 lstrip()和 rstrip()
string.swapcase()                                  翻转 string 中的大小写
string.title()                                     返回"标题化"的 string,就是说所有单词都是以大写开始，其余字母均为小                                                    写(见 istitle())
string.translate(str, del="")                      根据 str 给出的表(包含 256 个字符)转换 string 的字符,要过滤掉的字                                                    符放到 del 参数中                  
string.upper()                                     转换 string 中的小写字母为大写
string.zfill(width)                                返回长度为 width 的字符串，原字符串 string 右对齐，前面填充0
```

***



#### 列表

List（列表） 是 Python 中使用最频繁的数据类型。

列表可以完成大多数集合类的数据结构实现。它支持字符，数字，字符串甚至可以包含列表（即嵌套）。

列表用 **[ ]** 标识，是 python 最通用的复合数据类型。

列表中值的切割也可以用到变量 **[头下标:尾下标]** ，就可以截取相应的列表，从左到右索引默认 0 开始，从右到左索引默认 -1 开始，下标可以为空表示取到头或尾。

加号 **+** 是列表连接运算符，星号 ***** 是重复操作.

```
list = [ 'runoob', 786 , 2.23, 'john', 70.2 ]
tinylist = [123, 'john']
 
print list               # 输出完整列表
print list[0]            # 输出列表的第一个元素
print list[1:3]          # 输出第二个至第三个元素 
print list[2:]           # 输出从第三个开始至列表末尾的所有元素
print tinylist * 2       # 输出列表两次
print list + tinylist    # 打印组合的列表
```

序列是Python中最基本的数据结构。序列中的每个元素都分配一个数字 - 它的位置，或索引，第一个索引是0，第二个索引是1，依此类推。

Python有6个序列的内置类型，但最常见的是列表和元组。

序列都可以进行的操作包括索引，切片，加，乘，检查成员。

此外，Python已经内置确定序列的长度以及确定最大和最小的元素的方法。

列表是最常用的Python数据类型，它可以作为一个方括号内的逗号分隔值出现。

列表的数据项不需要具有相同的类型

创建一个列表，只要把逗号分隔的不同的数据项使用方括号括起来即可。如下所示：

```
list1 = ['physics', 'chemistry', 1997, 2000]
list2 = [1, 2, 3, 4, 5 ]
list3 = ["a", "b", "c", "d"]
```

与字符串的索引一样，列表索引从0开始。列表可以进行截取、组合等。

##### 访问列表中的值

使用下标索引来访问列表中的值，同样你也可以使用方括号的形式截取字符，如下所示：

```
list1 = ['physics', 'chemistry', 1997, 2000]
list2 = [1, 2, 3, 4, 5, 6, 7 ]
 
print "list1[0]: ", list1[0]
print "list2[1:5]: ", list2[1:5]
```

更新列表

你可以对列表的数据项进行修改或更新，你也可以使用append()方法来添加列表项，如下所示：

```
list = []          ## 空列表
list.append('Google')   ## 使用 append() 添加元素
list.append('Runoob')
print list
```

##### 删除列表元素

可以使用 del 语句来删除列表的元素，如下实例：

```
list1 = ['physics', 'chemistry', 1997, 2000]
 
print list1
del list1[2]
print "After deleting value at index 2 : "
print list1
```

##### 列表脚本操作符

列表对 + 和 * 的操作符与字符串相似。+ 号用于组合列表，* 号用于重复列表。

如下所示：

```
 表达式                          	结果	                      描述
len([1, 2, 3])	                  3                          长度
[1, 2, 3] + [4, 5, 6]	    [1, 2, 3, 4, 5, 6]	             组合
['Hi!'] * 4	                ['Hi!', 'Hi!', 'Hi!', 'Hi!']	 重复
3 in [1, 2, 3]                  	True	                 元素是否存在于列表中
for x in [1, 2, 3]: print x,	1 2 3	                     迭代
```

##### 列表截取

```

表达式  	结果	                  描述
L[2]	'Taobao'	             读取列表中第三个元素
L[-2]	'Runoob'	             读取列表中倒数第二个元素
L[1:]	['Runoob', 'Taobao']	 从第二个元素开始截取列表
```

##### 列表函数&方法

```
cmp(list1, list2)         比较两个列表的元素
len(list)                 列表元素个数
max(list)                 返回列表元素最大值
min(list)                 返回列表元素最小值
list(seq)                 将元组转换为列表
```

```
list.append(obj)                                     在列表末尾添加新的对象
list.count(obj)                                      统计某个元素在列表中出现的次数
list.extend(seq)                                     在列表末尾一次性追加另一个序列中的                                                                                多个值（用新列表扩展原来的列表）
list.index(obj)                                      从列表中找出某个值第一个匹配项的索引位置
list.insert(index, obj)                              将对象插入列表
list.pop([index=-1])                                 移除列表中的一个元素（默认最后一个元素），并且返回该元素的值
list.remove(obj)                                     移除列表中某个值的第一个匹配项
list.reverse()                                       反向列表中元素
list.sort(cmp=None, key=None, reverse=False)         对原列表进行排序
```

#### 元组

元组是另一个数据类型，类似于 List（列表）。

元组用 **()** 标识。内部元素用逗号隔开。但是元组不能二次赋值，相当于只读列表。

以下是元组无效的，因为元组是不允许更新的。而列表是允许更新的：

```
tuple = ( 'runoob', 786 , 2.23, 'john', 70.2 )
list = [ 'runoob', 786 , 2.23, 'john', 70.2 ]
tuple[2] = 1000    # 元组中是非法应用
list[2] = 1000     # 列表中是合法应用
```

访问/修改/删除/截取元组/元组 运算符/元组索引，与列表类似。

##### 无关闭分隔符

任意无符号的对象，以逗号隔开，默认为元组，如下实例：

```
print 'abc', -4.24e93, 18+6.6j, 'xyz'
x, y = 1, 2
print "Value of x , y : ", x,y
```

##### 元组内置函数

```
cmp(tuple1, tuple2)        比较两个元组元素。
len(tuple)                 计算元组元素个数。
max(tuple)                 返回元组中元素最大值。
min(tuple)                 返回元组中元素最小值。
tuple(seq)                 将列表转换为元组。
```



####  字典

字典(dictionary)是除列表以外python之中最灵活的内置数据结构类型。列表是有序的对象集合，字典是无序的对象集合。

两者之间的区别在于：字典当中的元素是通过键来存取的，而不是通过偏移存取。

字典用"{ }"标识。字典由索引(key)和它对应的值value组成。

##### 访问：

```
dict = {}
dict['one'] = "This is one"
dict[2] = "This is two"
 
tinydict = {'name': 'runoob','code':6734, 'dept': 'sales'}
 
 
print dict['one']          # 输出键为'one' 的值
print dict[2]              # 输出键为 2 的值
print tinydict             # 输出完整的字典
print tinydict.keys()      # 输出所有键
print tinydict.values()    # 输出所有值
```

输出：

```
This is one
This is two
{'dept': 'sales', 'code': 6734, 'name': 'runoob'}
['dept', 'code', 'name']
['sales', 6734, 'runoob']
```

##### 修改字典：

```
tinydict={'name':'lisa','age':8,'class':'first'}
tinydict['age'] = 10
print "tinydict['age']:",tinydict['age']
```

输出：

```
tinydict['Age']:  10
```

##### 删除字典元素

能删单一的元素也能清空字典，清空只需一项操作。

显示删除一个字典用del命令，如下实例：

```
tinydict = {'Name': 'Zara', 'Age': 7, 'Class': 'First'}
 
del tinydict['Name']  # 删除键是'Name'的条目
tinydict.clear()      # 清空字典所有条目
del tinydict          # 删除字典
 
print "tinydict['Age']: ", tinydict['Age'] 
print "tinydict['School']: ", tinydict['School']
```

##### 字典键的特性

1）不允许同一个键出现两次。创建时如果同一个键被赋值两次，后一个值会被记住

```
tinydict = {'Name': 'Runoob', 'Age': 7, 'Name': 'Manni'} 
 
print "tinydict['Name']: ", tinydict['Name']

##输出：
tinydict['Name']: Manni
```

2）键必须不可变，所以可以用数字，字符串或元组充当，所以用列表就不行

##### 字典内置函数&方法

###### 内置函数：

```
cmp(dict1, dict2) 比较两个字典元素。
len(dict)         计算字典元素个数，即键的总数。
str(dict)         输出字典可打印的字符串表示。
type(variable)    返回输入的变量类型，如果变量是字典就返回字典类型。
```

###### 内置方法：

```
dict.clear()                         删除字典内所有元素
dict.copy()                          返回一个字典的浅复制
dict.fromkeys(seq[, val])            创建一个新字典，以序列 seq 中元素做字典的键，val 为字典所有键对应的初始值
dict.get(key, default=None)          返回指定键的值，如果值不在字典中返回default值
dict.has_key(key)                    如果键在字典dict里返回true，否则返回false
dict.items()                         以列表返回可遍历的(键, 值) 元组数组
dict.keys()                          以列表返回一个字典所有的键
dict.setdefault(key, default=None)   和get()类似, 但如果键不存在于字典中，将会添加键并将值设为default
dict.update(dict2)                   把字典dict2的键/值对更新到dict里
dict.values()                        以列表返回字典中的所有值
pop(key[,default])                   删除字典给定键 key 所对应的值，返回值为被删除的值。key值必须给出。 否则，返回                                            default值。
popitem()                            返回并删除字典中的最后一对键和值。
```

#### 

### 数据类型转换

有时候，我们需要对数据内置的类型进行转换，数据类型的转换，你只需要将数据类型作为函数名即可。

以下几个内置的函数可以执行数据类型之间的转换。这些函数返回一个新的对象，表示转换的值。

```
函数	                        描述
int(x [,base])          将x转换为一个整数
long(x [,base] )        将x转换为一个长整数
float(x)                将x转换到一个浮点数
complex(real [,imag])   创建一个复数
str(x)                  将对象 x 转换为字符串
repr(x)                 将对象 x 转换为表达式字符串
eval(str)               用来计算在字符串中的有效Python表达式,并返回一个对象
tuple(s)                将序列 s 转换为一个元组
list(s)                 将序列 s 转换为一个列表
set(s)                  转换为可变集合
dict(d)                 创建一个字典。d 必须是一个序列 (key,value)元组。
frozenset(s)            转换为不可变集合
chr(x)                  将一个整数转换为一个字符
unichr(x)               将一个整数转换为Unicode字符
ord(x)                  将一个字符转换为它的整数值
hex(x)                  将一个整数转换为一个十六进制字符串
oct(x)                  将一个整数转换为一个八进制字符串
```



### Python 语句

#### 条件语句

Python条件语句是通过一条或多条语句的执行结果（True或者False）来决定执行的代码块。

Python程序语言指定任何非0和非空（null）值为true，0 或者 null为false。Python 编程中 if 语句用于控制程序的执行，基本形式为：

```
if 判断条件：
    执行语句……
else：
    执行语句……
```

if 语句的判断条件可以用>（大于）、<(小于)、==（等于）、>=（大于等于）、<=（小于等于）来表示其关系。当判断条件为多个值时，可以使用以下形式：

```
if 判断条件1:
    执行语句1……
elif 判断条件2:
    执行语句2……
elif 判断条件3:
    执行语句3……
else:
    执行语句4……
```

由于 python 并不支持 switch 语句，所以多个条件判断，只能用 elif 来实现，如果判断需要多个条件需同时判断时，可以使用 or （或），表示两个条件有一个成立时判断条件成功；使用 and （与）时，表示只有两个条件同时成立的情况下，判断条件才成功。

当if有多个条件时可使用括号来区分判断的先后顺序，括号中的判断优先执行，此外 and 和 or 的优先级低于>（大于）、<（小于）等判断符号，即大于和小于在没有括号的情况下会比与或要优先判断。

也可以在同一行的位置上使用if条件判断语句:

```
var = 100
if (var == 120):print var;
print 'goodbye!';

#输出：goodbye
```

####  循环语句

Python 提供了 for 循环和 while 循环（在 Python 中没有 do..while 循环）:

```
循环类型	                  描述
while 循环	   在给定的判断条件为 true 时执行循环体，否则退出循环体。
for 循环	       重复执行语句
嵌套循环	      可以在while循环体中嵌套for循环
```

#### 循环控制语句

循环控制语句可以更改语句执行的顺序。Python支持以下循环控制语句：

```
控制语句	                   描述
break 语句	     在语句块执行过程中终止循环，并且跳出整个循环
continue 语句	     在语句块执行过程中终止当前循环，跳出该次循环，执行下一次循环。
pass 语句   	     pass是空语句，是为了保持程序结构的完整性。
```

####  While 循环语句

```
while 判断条件(condition)：
    执行语句(statements)……
```

执行语句可以是单个语句或语句块。判断条件可以是任何表达式，任何非零、或非空（null）的值均为true。当判断条件假 false 时，循环结束。

while 语句时还有另外两个重要的命令 continue，break 来跳过循环，continue 用于跳过该次循环，break 则是用于退出循环，此外"判断条件"还可以是个常值，表示循环必定成立，具体用法如下：

```
i = 1
while i < 10:   
    i += 1
    if i%2 > 0:     # 非双数时跳过输出
        continue
    print i         # 输出双数2、4、6、8、10
 
i = 1
while 1:            # 循环条件为1必定成立
    print i         # 输出1~10
    i += 1
    if i > 10:     # 当i大于10时跳出循环
        break
```

#### 无限循环

如果条件判断语句永远为 true，循环将会无限的执行下去，

```
var = 1
while var == 1 :  # 该条件永远为true，循环将无限执行下去
   num = raw_input("Enter a number  :")
   print "You entered: ", num
 
print "Good bye!"
```

输出结果：

```
Enter a number  :20
You entered:  20
Enter a number  :29
You entered:  29
Enter a number  :3
You entered:  3
Enter a number between :Traceback (most recent call last):
  File "test.py", line 5, in <module>
    num = raw_input("Enter a number :")
KeyboardInterrupt
```

**注意：**以上的无限循环你可以使用 CTRL+C 来中断循环。

#### 循环使用 else 语句

在 python 中，while … else 在循环条件为 false 时执行 else 语句块：

```
count = 0
while count < 5:
   print count, " is  less than 5"
   count = count + 1
else:
   print count, " is not less than 5"
```

#### 简单语句组

类似 if 语句的语法，如果你的 while 循环体中只有一条语句，你可以将该语句与while写在同一行中， 如下所示：

```
flag = 1
 
while (flag): print 'Given flag is really true!'
 
print "Good bye!"
```

####  for 循环语句

Python for循环可以遍历任何序列的项目，如一个列表或者一个字符串。

**语法：**

for循环的语法格式如下：

```
for iterating_var in sequence:
   statements(s)
```

```
for letter in 'Python':     # 第一个实例
   print("当前字母: %s" % letter)
 
fruits = ['banana', 'apple',  'mango']
for fruit in fruits:        # 第二个实例
   print ('当前水果: %s'% fruit)
 
print ("Good bye!")
```

输出结果：

```
当前字母: P
当前字母: y
当前字母: t
当前字母: h
当前字母: o
当前字母: n
当前水果: banana
当前水果: apple
当前水果: mango
Good bye!
```

##### 通过序列索引迭代

另外一种执行循环的遍历方式是通过索引，如下实例：

```
fruits = ['banana', 'apple',  'mango']
for index in range(len(fruits)):
   print ('当前水果 : %s' % fruits[index])
 
print ("Good bye!")
```

输出：

```
当前水果 : banana
当前水果 : apple
当前水果 : mango
Good bye!
```

#### 循环使用 else 语句

在 python 中，for … else 表示这样的意思，for 中的语句和普通的没有区别，else 中的语句会在循环正常执行完（即 for 不是通过 break 跳出而中断的）的情况下执行，while … else 也是一样。

```
for num in range(10,20):  # 迭代 10 到 20 之间的数字
   for i in range(2,num): # 根据因子迭代
      if num%i == 0:      # 确定第一个因子
         j=num/i          # 计算第二个因子
         print ('%d 等于 %d * %d' % (num,i,j))
         break            # 跳出当前循环
   else:                  # 循环的 else 部分
      print ('%d 是一个质数' % num)
```

输出：

```
10 等于 2 * 5
11 是一个质数
12 等于 2 * 6
13 是一个质数
14 等于 2 * 7
15 等于 3 * 5
16 等于 2 * 8
17 是一个质数
18 等于 2 * 9
19 是一个质数
```

#### 循环嵌套

Python 语言允许在一个循环体里面嵌入另一个循环。

##### **for 循环嵌套语法：**

```
for iterating_var in sequence:
   for iterating_var in sequence:
      statements(s)
   statements(s)
```

##### ** while循环嵌套语法：**

```
while expression:
   while expression:
      statement(s)
   statement(s)
```

可以在循环体内嵌入其他的循环体，如在while循环中可以嵌入for循环， 反之，你可以在for循环中嵌入while循环。

```
##实例：嵌套循环2~100之间的素数
i = 2
while(i < 100):
   j = 2
   while(j <= (i/j)):
      if not(i%j): break
      j = j + 1
   if (j > i/j) : print i, " 是素数"
   i = i + 1
 
print "Good bye!"
```

#### break 语句

break语句用来终止循环语句，即循环条件没有False条件或者序列还没被完全递归完，也会停止执行循环语句。

break语句用在while和for循环中。

如果您使用嵌套循环，break语句将停止执行最深层的循环，并开始执行下一行代码。

**break 语句语法：**

```
break
```

实例：

```
for letter in 'Python':     # 第一个实例
   if letter == 'h':
      break
   print '当前字母 :', letter
  
var = 10                    # 第二个实例
while var > 0:              
   print '当前变量值 :', var
   var = var -1
   if var == 5:   # 当变量 var 等于 5 时退出循环
      break
 
print "Good bye!"
```

#### continue 语句

continue 语句跳出本次循环，而break跳出整个循环。

continue 语句用来告诉Python跳过当前循环的剩余语句，然后继续进行下一轮循环。

continue语句用在while和for循环中。

语言 continue 语句语法格式如下：

```
continue
```

#### pass 语句

pass 是空语句，是为了保持程序结构的完整性。

**pass** 不做任何事情，一般用做占位语句。

语言 pass 语句语法格式如下：

```
pass
```

实例：

```
for letter in 'Python':
   if letter == 'h':
      pass
      print '这是 pass 块'
   print '当前字母 :', letter
 
print "Good bye
```

输出：

```
当前字母 : P
当前字母 : y
当前字母 : t
这是 pass 块
当前字母 : h
当前字母 : o
当前字母 : n
Good bye!
```

#### math 模块、cmath 模块

Python 中数学运算常用的函数基本都在 math 模块、cmath 模块中。

math 模块提供了许多对浮点数的数学运算函数。

 cmath 模块包含了一些用于复数运算的函数。

cmath 模块的函数跟 math 模块函数基本一致，区别是 cmath 模块运算的是复数，math 模块运算的是数学运算。

要使用 math 或 cmath 函数必须先导入：

```
import math
```

查看 math 查看包中的内容:

```
>>> import math
>>> dir(math)
['__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atan2', 'atanh', 'ceil', 'copysign', 'cos', 'cosh', 'degrees', 'e', 'erf', 'erfc', 'exp', 'expm1', 'fabs', 'factorial', 'floor', 'fmod', 'frexp', 'fsum', 'gamma', 'gcd', 'hypot', 'inf', 'isclose', 'isfinite', 'isinf', 'isnan', 'ldexp', 'lgamma', 'log', 'log10', 'log1p', 'log2', 'modf', 'nan', 'pi', 'pow', 'radians', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau', 'trunc']
>>>
```

查看 cmath 查看包中的内容：

```
>>> import cmath
>>> dir(cmath)
['__doc__', '__file__', '__loader__', '__name__', '__package__', '__spec__', 'acos', 'acosh', 'asin', 'asinh', 'atan', 'atanh', 'cos', 'cosh', 'e', 'exp', 'inf', 'infj', 'isclose', 'isfinite', 'isinf', 'isnan', 'log', 'log10', 'nan', 'nanj', 'phase', 'pi', 'polar', 'rect', 'sin', 'sinh', 'sqrt', 'tan', 'tanh', 'tau']
>>>
```

```
>>> import cmath
>>> cmath.sqrt(-1)
1j
>>> cmath.sqrt(9)
(3+0j)
>>> cmath.sin(1)
(0.8414709848078965+0j)
>>> cmath.log10(100)
(2+0j)
>>>
```



### 数学函数

```
函数	                     返回值 ( 描述 )
abs(x)	                  返回数字的绝对值，如abs(-10) 返回 10
ceil(x)	                  返回数字的上入整数，如math.ceil(4.1) 返回 5
cmp(x, y)	              如果 x < y 返回 -1, 如果 x == y 返回 0, 如果 x > y 返回 1
exp(x)	                  返回e的x次幂(ex),如math.exp(1) 返回2.718281828459045
fabs(x)	                  返回数字的绝对值，如math.fabs(-10) 返回10.0
floor(x)	              返回数字的下舍整数，如math.floor(4.9)返回 4
log(x)	                  如math.log(math.e)返回1.0,math.log(100,10)返回2.0
log10(x)	              返回以10为基数的x的对数，如math.log10(100)返回 2.0
max(x1, x2,...)	          返回给定参数的最大值，参数可以为序列。
min(x1, x2,...)	          返回给定参数的最小值，参数可以为序列。
modf(x)	                  返回x的整数部分与小数部分，两部分的数值符号与x相同，整数部分以浮点型表示。
pow(x, y)	              x**y 运算后的值。
round(x [,n])	          返回浮点数x的四舍五入值，如给出n值，则代表舍入到小数点后的位数。
sqrt(x)	                  返回数字x的平方根
```

#### 随机数函数

Python包含以下常用随机数函数：

```
函数	                                          描述
choice(seq)	                      从序列的元素中随机挑选一个元素，比如                                                                               random.choice(range(10))，从0到9中随机挑选一个整数。
randrange ([start,] stop [,step]) 从指定范围内，按指定基数递增的集合中获取一个随机数，基数默认值为 1
random()	                      随机生成下一个实数，它在[0,1)范围内。
seed([x])	                      改变随机数生成器的种子seed。如果你不了解其原理，你不必特别去设定seed，Python会帮你选择                                   seed。
shuffle(lst)	                  将序列的所有元素随机排序
uniform(x, y)	                  随机生成下一个实数，它在[x,y]范围内。
```

#### 三角函数

```
函数	                       描述
acos(x)	              返回x的反余弦弧度值。
asin(x)	              返回x的反正弦弧度值。
atan(x)	              返回x的反正切弧度值。
atan2(y, x)	          返回给定的 X 及 Y 坐标值的反正切值。
cos(x)	              返回x的弧度的余弦值。
hypot(x, y)	          返回欧几里德范数 sqrt(x*x + y*y)。
sin(x)	              返回的x弧度的正弦值。
tan(x)	              返回x弧度的正切值。
degrees(x)	          将弧度转换为角度,如degrees(math.pi/2) ， 返回90.0
radians(x)	          将角度转换为弧度
```

#### 数学常量

```
常量	描述
pi	数学常量 pi（圆周率，一般以π来表示）
e	数学常量 e，e即自然常数（自然常数）。
```



### 函数

语法：

```
def function(parameters):
     "函数_文档字符串"
     function_suite
     return [expressions]
##以 def 关键词开头，后接函数标识符名称和圆括号()。
  任何传入参数和自变量必须放在圆括号中间。圆括号之间可以用于定义参数。
  函数的第一行语句可以选择性地使用文档字符串—用于存放函数说明。
  函数内容以冒号起始，并且缩进。
  return [表达式] 结束函数，选择性地返回一个值给调用方。不带表达式的return相当于返回 None。
```

实例：

```
def printme( str ):
   "打印传入的字符串到标准显示设备上"
   print str
   return
```

函数的调用：

定义一个函数只给了函数一个名称，指定了函数里包含的参数，和代码块结构。

这个函数的基本结构完成以后，可以通过另一个函数调用执行，也可以直接从Python提示符执行。

如下实例调用了printme（）函数：

```
# 定义函数
def printme( str ):
   "打印任何传入的字符串"
   print str
   return
 
# 调用函数
printme("我要调用用户自定义函数!")
printme("再次调用同一函数")
```

输出：

```
我要调用用户自定义函数!
再次调用同一函数
```

#### 参数传递

在 python 中，strings, tuples, 和 numbers 是不可更改的对象，而 list,dict 等则是可以修改的对象。

```
def ChangeInt( a ):
    a = 10
 
b = 2
ChangeInt(b)
print b # 结果是 2
```

可变：

```
# 可写函数说明
def changeme( mylist ):
   "修改传入的列表"
   mylist.append([1,2,3,4])
   print "函数内取值: ", mylist
   return
 
# 调用changeme函数
mylist = [10,20,30]
changeme( mylist )
print "函数外取值: ", mylist

##输出：
函数内取值:  [10, 20, 30, [1, 2, 3, 4]]
函数外取值:  [10, 20, 30, [1, 2, 3, 4]]
```

#### 参数

以下是调用函数时可使用的正式参数类型：

- 必备参数

调用函数时数量必须跟声明时的一样，且需传入一个参数。

- 关键字参数

函数调用时需要使用关键字参数来确定传入的参数值。允许参数的顺序跟声明时不一样。

```
#可写函数说明
def printinfo( name, age ):
   "打印任何传入的字符串"
   print "Name: ", name
   print "Age ", age
   return
 
#调用printinfo函数
printinfo( age=50, name="miki" )
```

输出：

```
Name:  miki
Age  50
```



- 默认参数

调用函数时，默认参数的值如果没有传入，则被认为是默认值

```
#可写函数说明
def printinfo( name, age = 35 ):
   "打印任何传入的字符串"
   print "Name: ", name
   print "Age ", age
   return
 
#调用printinfo函数
printinfo( age=50, name="miki" )
printinfo( name="miki" )
```

输出：

```
Name:  miki
Age  50
Name:  miki
Age  35
```

- 不定长参数

一个函数能处理比当初声明时更多的参数。

```
def functionname([formal_args,] *var_args_tuple ):
   "函数_文档字符串"
   function_suite
   return [expression]
```

加了星号（*）的变量名会存放所有未命名的变量参数:

```
# 可写函数说明
def printinfo( arg1, *vartuple ):
   "打印任何传入的参数"
   print "输出: "
   print arg1
   for var in vartuple:
      print var
   return
 
# 调用printinfo 函数
printinfo( 10 )
printinfo( 70, 60, 50 )
```

输出：

```
输出:
10
输出:
70
60
50
```

### 匿名函数

python 使用 lambda 来创建匿名函数。

- lambda只是一个表达式，函数体比def简单很多。
- lambda的主体是一个表达式，而不是一个代码块。仅仅能在lambda表达式中封装有限的逻辑进去。
- lambda函数拥有自己的命名空间，且不能访问自有参数列表之外或全局命名空间里的参数。
- 虽然lambda函数看起来只能写一行，却不等同于C或C++的内联函数，后者的目的是调用小函数时不占用栈内存从而增加运行效率。

#### 语法

lambda函数的语法只包含一个语句，如下：

```
lambda [arg1 [,arg2,.....argn]]:expression
```

```
# 可写函数说明
sum = lambda arg1, arg2: arg1 + arg2 
# 调用sum函数 
print "相加后的值为 : ", sum( 10, 20 )
print "相加后的值为 : ", sum( 20, 20 )
```

以上实例输出结果：

```
相加后的值为 :  30
相加后的值为 :  40
```

#### return 语句

return语句[表达式]退出函数，选择性地向调用方返回一个表达式。不带参数值的return语句返回None

```
# 可写函数说明
def sum( arg1, arg2 ):
   # 返回2个参数的和."
   total = arg1 + arg2
   print "函数内 : ", total
   return total
 
# 调用sum函数
total = sum( 10, 20 )
```

输出：

```
函数内：30
```



###  模块

Python 模块(Module)，是一个 Python 文件，以 .py 结尾，包含了 Python 对象定义和Python语句。

模块能定义函数，类和变量，模块里也能包含可执行的代码。

support.py 模块：

```
def print_func( par ):
   print "Hello : ", par
   return
```



#### import 语句

###### 模块的引入

模块定义好后，我们可以使用 import 语句来引入模块，语法如下：

```
import module1[, module2[,... moduleN]]
```

比如要引用模块 math，就可以在文件最开始的地方用 **import math** 来引入。在调用 math 模块中的函数时，必须这样引用：

```
模块名.函数名
```

当解释器遇到import时，如果模块在当前的搜索路径就会被导入，例子：导入test.py文件代码：

```
# 导入模块
import support
 
# 现在可以调用模块里包含的函数了
support.print_func("Runoob")
```

#### from…import 语句

Python 的 from 语句让你从模块中导入一个指定的部分到当前命名空间中。语法如下：

```
from modname import name1[, name2[, ... nameN]]
```

例如，要导入模块 fib 的 fibonacci 函数，使用如下语句：

```
from fib import fibonacci
```

这个声明不会把整个 fib 模块导入到当前的命名空间中，它只会将 fib 里的 fibonacci 单个引入到执行这个声明的模块的全局符号表。

#### from…import* 语句

把一个模块的所有内容全都导入到当前的命名空间也是可行的，只需使用如下声明：

```
from modname import *
```

这提供了一个简单的方法来导入一个模块中的所有项目。然而这种声明不该被过多地使用。

例如我们想一次性引入 math 模块中所有的东西，语句如下：

```
from math import *
```

#### dir()函数

dir() 函数一个排好序的字符串列表，内容是一个模块里定义过的名字。

返回的列表容纳了在一个模块里定义的所有模块，变量和函数。如下一个简单的实例：

#### globals() 和 locals() 函数

根据调用地方的不同，globals() 和 locals() 函数可被用来返回全局和局部命名空间里的名字。

如果在函数内部调用 locals()，返回的是所有能在该函数里访问的命名。

如果在函数内部调用 globals()，返回的是所有在该函数里能访问的全局名字。

两个函数的返回类型都是字典。所以名字们能用 keys() 函数摘取。



------

#### reload() 函数

当一个模块被导入到一个脚本，模块顶层部分的代码只会被执行一次。

因此，如果你想重新执行模块里顶层部分的代码，可以用 reload() 函数。该函数会重新导入之前导入过的模块。语法如下：

```
reload(module_name)
```

在这里，module_name要直接放模块的名字，而不是一个字符串形式。比如想重载 hello 模块，如下：

```
reload(hello)
```

#### 包

包是一个分层次的文件目录结构，它定义了一个由模块及子包，和子包下的子包等组成的 Python 的应用环境。

简单来说，包就是文件夹，但该文件夹下必须存在 __init__.py 文件, 该文件的内容可以为空。**__init__.py** 用于标识当前文件夹是一个包。

考虑一个在 **package_runoob** 目录下的 **runoob1.py、runoob2.py、__init__.py** 文件，test.py 为测试调用包的代码，目录结构如下：

```
test.py
package_runoob
|-- __init__.py
|-- runoob1.py
|-- runoob2.py
```