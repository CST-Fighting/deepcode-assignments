## JavaScript

- #### 基本语法

##### 执行顺序

按照再HTML文件中出现的顺序逐行执行。如果徐娅在整个HTML文件中执行（如函数/全局变量等），那么最好将其放在HTML文件的<head>...</head>标签中。某些代码，如函数体内的代码，不会立即执行，只有当所在的函数被其他程序调用时，该代码才会被执行。

字母大小写敏感

严格区分字母大小写，而HTML不区分大小写字母。

空格与换行

在JavaScript中会忽略程序中的空格/换行/制表符，除非这些符号是字符串/正则表达式中的一部分。因此可以在JavaScript中随意使用这些符号进行排版。

```
#JavaScript中的换行有”断句“的意思，即换行能判断一条语句是否已经结束，代码：
a = 100
return false
```

```
#如果将第二行代码完成
return 
false
```

每行结尾的分号可有可无

```
#以下两行代码均正确
alert ("Welcome to China!")
alert ("Welcome to China!");    #最好还是加上分号
```

##### 注释

```
两种注释符号：“//”（单行注释）和“/*...*/”（多行注释）
```



#### 数据类型

##### 数值型

1）十进制，整数是0~9组成的数字序列（数字格式允许精确表示-2^（53）、2^(53)，但有些整数运算是对32位的整数执行，范围-2^(32)到（2^(31)-1）。

2）八进制（0~7）

3）十六进制（以0X或者0x开头），数字是0~9以及a（A）~f(F)之间的字母，来表示0~15。

4）浮点型数据：传统计数法（如果整数部分为0，则可以省略整数部分）、科学计数法（实数后跟字母e或E（数值×10），后面加上一个带正/负号的整数指数，其中正号可省）

5）特殊值Infinity(无穷大，超出最大值时，输出)

超出最小值时，输出-infinity

6)特殊值NaN(Not a Number,非数字)

```
alert(0/0);     #输出0/0的值，为NaN
```



##### 字符串型（String）

由0个或多个字符组成的序列，包含大小写字母、数字、标点符号或其他字符，也可以包含汉字。是JavaScript用来表示文本的数据类型。JavaScript程序中的字符串型数据是包含在单引号/双引号中的，由单引号定界的字符串中可以含有双引号，由双引号定界的字符串中也可以含有 单引号。空字符串不包含任何字符，也不包含任何空格，用一对引号表示，即“”或“。

注意：包含字符串的引号必须匹配。若在字符串前使用双引号，则其后也必须是双引号；单引号也是。

```
‘你好 JavaScript！’
”你好 JavaScript！“
‘abc"efg'    #单引号定界的字符串中可以含有双引号，双中也可以含有单。

```

##### 转义字符

```
\b 退格
\f 走纸换页
\n 换行
\r 回车
\t 横向跳格 (Ctrl-I)
\' 单引号
\" 双引号
\\ 反斜杠
\v 垂直制表符
\r 回车符
\\ 反斜杠
\OOO 八进制，范围000~777
\xHH 十六进制整数，范围00~FF
\uhhhh  十六进制编码的Unicode字符
```

##### 布尔型

两个值：true、false【也可以是on、off】



特殊数据类型

未定义值（undefined），表示变量还没有被赋值（如：var a;）

空值（null）



##### 常量和变量

常量【在程序运行中保持不变的数据】

```
123                    #数值型常量
"javascripts"          #字符串型常量
true/false             #布尔型常量
```

##### 变量

1）命名

规则：

```
必须以字母/下划线开头 ，其他字符可以是数字、字母、下划线
变量名不能包含空格/加号/减号等符号
严格区分大小写
不能使用JavaScript中的关键字
```

```
##常用关键字
名称                              作用
break              立即退出循环，阻止再次反复执行任何代码
case               配合switch完成判断
catch              配合try进行错误判断
continue           退出当前循环，根据控制表达式还允许继续进行下一次循环
default            配合switch，当条件不存在时使用该项
delete             删除了一个属性
do                 用于do-while,后测试循环，即退出条件在执行循环内部的代码之后计算
else               配合if条件判断，用于条件选择的跳转
finally            预防出现异常时用的，无论异常是否是否发生异常都会处理的
for                for语句，循环语句
function           函数关键字
if                 if 语句用于判断
in                 1.配合for遍历对象，2.判断某个属性属于某个对象
instanceof         某个对象是不是另一个对象的实例
new                创建一个新对象
return             从当前函数退出，并从那个函数返回一个值
switch             弥补if的多重判断语句
this               总是指向调用该方法的对象
throw              抛出异常
try                配合catch进行错误判断
typeof             检测变量的数据类型
var                声明变量
void               声明没有返回值
while              while判断语句，可配合do做前置判断，或独立使用做后置判断
with               with 语句用于设置代码在特定对象中的作用域
```

```
#JavaScript常用的保留字
abstract      boolean        byte          char
class         const          debugger      double
enum          export         extends       final
float         goto           implements    import
int          interface       long          native
package      private         protected     public
short         static         super       synchronized
throws     transient         volatile
```

2）声明（用关键字var）

```
var variablename;
var a,b,c;                #可同时声明多个变量
```

3）变量赋值

可以使用等于号（=）对变量初始化赋值，例如：

```
var lesson="JavaScript学习";       #声明变量lesson，并赋值为“JavaScript学习”，也可以
var lesson1;lesson1="javascript";
```

也可以不限声明直接赋值，例如：

```
str = "这是一个未声明的变量";     #给未声明的变量赋值
document.write(str);          #输出变量值
```

若只声明未赋值，那么其值默认为undefined。

4）变量类型【变量的值所属的数据类型，可以是数值型、字符串型、布尔型等】



#### 运算符

##### 1）算术运算符

```
+
-
*
/
%
++     自增符号，分两种情况：i++（在使用i之后使i的值+1）、++i（在使用i之前先使i的值+1）
--     自减符号，分两种情况：i--（在使用i之后使i的值减一）、--i（在使用i之前先使i的值减一）
```

##### 2）字符串运算符

```
+       连接两个字符串
+=      连接拉零个字符串并将结果赋给第一个字符串
例如：
var name="学习";
name +="javascript";    #相当于name = name+"JavaScript";
```

注：JavaScript脚本会根据操作数的数据类型来确定”+“是算术运算符，还是字符串运算符。在两个操作数中，只要有一个是字符串类型的，那么”+“就是字符串运算符。

##### 3）比较运算符

返回值：true、false

```
>
<
<=
>=
==
===    #绝对等于    ”17“=17  返回false
!=     #不等于
!==    #不绝对等于  ”17“！==17 返回true
```

##### 4）赋值运算符

```
=
+=
-=
*=
/=
%=      #a%=b 相当于a=a%b
```

##### 5)逻辑运算符

```
&&     #逻辑与 ，a&&b,只有a、b都为真，才返回true
||     #逻辑或 ，a||b,只要a或b为真，返回true，否则false
！     #逻辑非 ，!a,当a为假时，返回true，否则为false
```

##### 6）条件运算符

```
表达式?结果1:结果2      #若表达式为true，则整个表达式的结果为”结果1“；否则为”结果2“.
```

##### 7）其他运算符

逗号运算符

可将多个表达式排在一起，整个表达式的值为最后一个表达式的值。

```
var a,b,c,d;
a=(b=3,c=5,d=6);
alert("a的值为"+a)
```

##### 8）typeof运算符

用于判断操作数的数据类型。它可以返回一个字符串，该字符串说明了操作数是什么数据类型，语法：

```
typeof 操作数
```

```
#不同类型的操作数使用typeof运算符的返回值
数据类型              返回值
数值                 number
字符串                string
布尔值               Boolean
undefined           undefined
null                object
对象                 object
函数                 function
```

##### 9）new运算符

可用来创建一个新的内置对象，语法：

```
对象实例名称 = new 对象类型(参数)
对象实例名称 = new 对象类型
```

实例：

```
Object1 = new Object;                #创建自定义对象
Array2 = new Array();                #创建数组对象
Date3 = new Date("August 8 2008");   #创建日期对象
```

##### 10）运算符的优先级与结合性

```
        优先级从高到低

运算符                                                              描述
. [] ()                                               字段访问、数组下标、函数调用以及表达式分组
++ -- - ~ ! delete new typeof void                    一元运算符、返回数据类型、对象创建、未定义值
* / %                                                 乘法、除法、取模
+ - +                                                 加法、减法、字符串连接
<< >> >>>                                             移位
< <= > >= instanceof                                  小于、小于等于、大于、大于等于、instanceof
== != === !==                                         等于、不等于、严格相等、非严格相等
&                                                     按位与
^                                                     按位异或
|                                                     按位或
&&                                                    逻辑与
||                                                    逻辑或
?:                                                    条件
= oP=                                                 赋值、运算赋值
,                                                     多重求值
```

##### 表达式

是运算符和操作数组合而成的式子，表达式的值就是对操作数进行运算后的结果。

按其运算结果可分为:算术运算符、字符串运算符、逻辑运算符





#### 数据类型转换

###### 1）转为字符串：使用.toString或者String

.toString方法：

```
var bool=true;
console.log(bool.toString());    #注意：.toString不能转为null和undefined 
```

String()方法：

```
console.log(bool.String());     #String()方法都能转
```

隐式转换：num+""  ,当+两边一个操作符为字符串类型，一个操作符是其他类型的时候，会先把其他类型转换成字符串再进行拼接，返回字符串。

```
var a = true;
var str = a+"";
console.log('str');
```

###### 2)转为数值类型

Number():Number()可以把任意值转换为数值，若要转换的字符串中有一个不是数值的字符，返回NaN

```
console.log(Number(true));
```

parseInt():

```
var a="12.3px";
console.log(parseInt(a);
//结果：12.3.  如果第一个字符是数字会解析知道遇到非数字结束.
var a="abc2.3";
console.log(parseInt(a);
结果：返回NaN，如果第一个字符不是数字或者符号就返回NaN.
```

parseFloat():

将字符串转换成浮点数，它跟parseInt()很相似 ，不同的是，parseFloat()会解析第一个。遇到第二个或者非数字，结束。如果解析里的内容只有整数，解析成整数。

隐式转换：

```
var str = "123";
var num = str - 0;
console.log(num);      #结果为数值型
```

###### 3）转换为Boolean(): 0  ”（非空字符串）null  undefined NaN会转换成false，其他的都会转换成true。

方法：

```
#1.boolean():
console.log(boolean(2));
#2.
var message;
if(message){};
#3.隐式转换
var str = "123";
var bool = !!str;
console.log(str);
```

###### 4)转换为逻辑型

```
 类型                    转换后的结果
undefined                 false
null                      false
数值型                     若其值为0或NaN，则结果为false；否则为true
字符串型                   若其长度为0，结果为false；否则为true
其他对象                    True
```



###### 5)其他转换

```
类型                               转换结果
undefined                          NaN
null                                0
逻辑型                              若其值为true，则结果为1；其值为false，结果为0
字符串型                            若内容为数字，结果为相应的数字；否则为NaN
其他对象                             NaN
```





- #### 函数

函数的定义和调用

基本语法：

```
function 函数名([参数1，参数2，...]){
语句
[return 返回值]
}
#说明：函数名：必选，同一页面唯一，区分字母大小写
参数：可用逗号隔开，，最多255个参数
语句：实现函数功能的语句
返回值:可为任意表达式、变量、常量，可选，用于返回函数值
```

例子：

```
function account(price,number){           #定义含有两个参数的函数
var sum = price * number;                 #计算金额
return sum;                               #返回计算后的金额
}
```

##### 函数的调用

1）简单语法：

```
函数名(传递给函数的参数1，传递给函数的参数2，...)；
```

2）在事件响应中调用函数

当用户单击某个按钮/复选框时将触发事件，通过编写程序对事件做出反应的行为称为响应事件。

3）通过单击链接调用函数

```
<script type="text/javascript">
   function test(){                                 //定义函数
   alert("I love programming");                     //定义函数体
   }
</script>
<a href = "javascript:test()">单击链接</a>            <!--在链接中调用自定义函数-->
```

##### 函数的参数

语法：

```
function 函数名(形参1，形参2，...){
  函数体
}
```

若函数有参数，则：

```
函数名 (实参1，实参2，...)
```

函数返回值

语法：

```
return 表达式;
```

##### 嵌套函数

1）定义：在函数内部再定义其他的函数

```
function outfun(){               #定义外部函数
    function infun(x,y){          #定义内部函数
    alert(x+y);                   #输出两个参数的和
    }
    infun(1,5);                    #调用内部函数并传递参数
}
outfun();                            #调用外部函数
```

2）函数嵌套调用

```
function a(){                  #定义函数a()
     alert("learning javascript!");     #输出字符串
}
function b(){       #定义函数b()
    a();             #在函数b()中调用a()函数
}
b();              #调用函数b()
```

##### 递归函数

定义：在自身函数的函数体调用自身。

语法：

```
function 函数名（参数1）{
      函数名(参数2);
}

##递归函数的两个必要条件：
1.包括一个结束递归的条件
2.包括一条递归调用的语句
```

实例：

```
function f(num){
    if(num<=1){   #结束递归的条件
    return 1;
    }else{
    return f(num-1)*num;   #调用递归函数
    }
}
alert("10!的结果为：" + f(10));
```



##### 内置函数

```
函数                                  说明
parseInt(string,[n])              字符串型转换为整型
parseFloat(string)                字符串型转换为浮点型
isNaN(num)                        判断一个数值是否为NaN
isFinite(num)                     判断是否有限
eval(string)                      求字符串中表达式的值  
encodeURI(url)                       对URI字符串进行编码
decodeURI(url)                       对已经编码的URI字符串进行编码
```

```
var URI="http://127.0.0.1/save.html?name=测试";   #定义URI字符串
document.write(encodeURI(URI));    #对URI字符串进行编码并输出
```

##### 匿名函数

```
var 变量名 = function(参数1，参数2，...){
  函数体;
}
```

2）使用Function（）构造函数来定义函数

```
var 变量名 = new Function("参数1"，“参数2”，....，“函数体”)；
```

```
var sum = new Function("x","y","alert(x+y);");   #使用Function()构造函数定义函数
sum(10,20);     #调用函数
```



#### 对象

##### 对象属性和方法

1）属性

```
对象名.属性名
var name = 用户.用户名;
var password = 用户.密码;
```

2)对象方法

```
对象名.方法名(参数)     #可多个参数
```

调用对象：

```
用户.注册();
用户.登录();

```

3）对象种类

JavaScript语言中的对象可分为三种类型：

用户定义对象（user-defined object）：由程序员自行创建的对象
内建对象（native object）：内建在JS语言中的对象，即Array，Math等
宿主对象（host object）：有浏览器提供的对象。

内置对象中常用的：Math,Date,String,Number,Array,Boolean,Global,Object,RegExp等



##### 自定义对象的创建

1）直接创建：

```
var 对象名 = {属性名1：属性值1，属性名2：属性值2，...}
```

2）通过自定义构造函数创建对象

```
function student(name,sex,age){
    this.name=name;    #初始化对象的name属性
    this.sex=sex;
    this.age=age;
}
function showName(){     #定义showName()方法
alert(this.name);          #输出属性值
}
```

prototype属性，可向对象中添加属性/方法：

```
object.prototype.name=value;   #object，构造函数名  name,添加的属性名/方法名   value，添加属性的值/执行方法的函数
```

3）通过object对象创建自定义对象

语法：

```
obj = new object([value])    #value可为Numer，Boolean，String类型的数据。若value为null或undefined或没有给出，则产生                                                                                     没有内容的对象
```



##### 对象访问语句

1）for...in语句

语法：

```
for(变量 in 对象){
语句;
}
```

2)with语句

用于访问一个对象的属性/方法时避免重复引用指定的对象名

```
with(对象名称){
语句
}
```



##### 常用的内部对象

Math对象

```
Math.random();                  //随机0~1之间的数值
Math.abs(x);                    //绝对值
Math.ceil(x);                   //向上取整，如4.1 --> 5, (-5.9) --> (-5)
Math.round(x);                 //四舍五入，如（-5.52）-->-6
Math.floor(x);                 //向下取整
Math.max(x,y);                 //最大
Math.min(x,y);                //最小
Math.pow(x,y);                //x的y次方
Math.sqrt(x);                 //开方
```

Date对象

```
var now = new date();
now;                                   //2017-07-15T15:04:31.807Z
now.getFullYear();                     //2017
now.setFullYear(2017);                 //设定年份，下面的都可以这样设置
now.getMonth();                        //6，注意！！！月份范围是0~11，6表示7月！！
now.getDate();                         //15
now.getDay();                          //6,这是星期
now.getHours();                        //23
now.getMinutes();                      //11
now.getSeconds();                      //23
now.getMilliseconds();                 //49,毫秒
now.getTime();                         //1500131686539，时间戳
```



- 作用域（作用域链）

变量的作用域

1）全局变量、局部变量

全局变量：定义在所有函数外的变量，作用范围是该变量定义后的所有代码

局部变量：定义在函数体内的变量，只有在该函数中，且变量定义之后的代码才可以使用这个变量，函数参数也是局部性的，只在函数内部起作用。

```
var a = "这是全局变量";     #该变量在函数外声明，作用于整个脚本
function send(){          #定义函数
   var b = "这是局部变量";   #该变量在函数内声明，只作用于该函数体
   document.write(a+"<br>");    #输出全局变量的值
   document.write(b);           #输出局部变量的值
}
send();  #调用函数
```

2）变量的优先级

```
var a="这是全局变量";
function send(){
   var a = "这是局部变量";
   document.write(a);   
}
send();
```



#### BOM&DOM

DOM（文档对象模型）是 HTML 和 XML 的应用程序接口（API）。

BOM 主要处理浏览器窗口和框架，不过通常浏览器特定的 JavaScript 扩展都被看做 BOM 的一部分。这些扩展包括

```
弹出新的浏览器窗口
移动、关闭浏览器窗口以及调整窗口大小
提供 Web 浏览器详细信息的定位对象
提供用户屏幕分辨率详细信息的屏幕对象
对 cookie 的支持
IE 扩展了 BOM，加入了 ActiveXObject 类
```

javacsript是通过访问BOM（Browser Object Model）对象来访问、控制、修改客户端(浏览器)，由于BOM的window包含了document，window对象的属性和方法是直接可以使用而且被感知的，因此可以直接使用window对象的document属性，通过document属性就可以访问、检索、修改XHTML文档内容与结构。因为document对象又是DOM（Document Object Model）模型的根节点。可以说，BOM包含了DOM(对象)，浏览器提供出来给予访问的是BOM对象，从BOM对象再访问到DOM对象，从而js可以操作浏览器以及浏览器读取到的文档。其中
DOM包含：window

```
Window对象包含属性：document、location、navigator、screen、history、frames
Document根节点包含子节点：forms、location、anchors、images、links        
```

