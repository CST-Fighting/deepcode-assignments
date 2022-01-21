## ❗ let 和 const

### HTML 代码中使用全局变量

在 JavaScript 中, 全局作用域是针对 JavaScript 环境。

在 HTML 中, 全局作用域是针对 window 对象。

使用 **var** 关键字声明的全局作用域变量属于 window 对象:

实例

```
var carName = "Volvo"; // 可以使用 window.carName 访问变量
```

使用 **let** 关键字声明的全局作用域变量不属于 window 对象:

```
let carName = "Volvo";
// 不能使用 window.carName 访问变量
```

重置变量

使用 **var** 关键字声明的变量在任何地方都可以修改：

实例

```
var x = 2;  // x 为 2  var x = 3;  // 现在 x 为 3
```

在相同的作用域或块级作用域中，不能使用 **let** 关键字来重置 **var** 关键字声明的变量:

```
var x = 2;       // 合法
let x = 3;       // 不合法

{
    var x = 4;   // 合法
    let x = 5   // 不合法
}
```

在相同的作用域或块级作用域中，不能使用 **let** 关键字来重置 **let** 关键字声明的变量:

```
let x = 2;       // 合法
let x = 3;       // 不合法

{
    let x = 4;   // 合法
    let x = 5;   // 不合法
}
```

在相同的作用域或块级作用域中，不能使用 **var** 关键字来重置 **let** 关键字声明的变量:

```
let x = 2;       // 合法
var x = 3;       // 不合法

{
    let x = 4;   // 合法
    var x = 5;   // 不合法
}
```

**let** 关键字在不同作用域，或不同块级作用域中是可以重新声明赋值的:

```
let x = 2;       // 合法

{
    let x = 3;   // 合法
}

{
    let x = 4;   // 合法
}
```

变量提升
JavaScript 中，var 关键字定义的变量可以在使用后声明，也就是变量可以先使用再声明（JavaScript 变量提升）。

实例

```
// 在这里可以使用 carName 变量
 
var carName;
```

```
let 关键字定义的变量则不可以在使用后声明，也就是变量需要先声明再使用。

// 在这里不可以使用 carName 变量
let carName;
```

const 关键字
const 用于声明一个或多个常量，声明时必须进行初始化，且初始化后值不可再修改：

```
实例
const PI = 3.141592653589793;
PI = 3.14;      // 报错
PI = PI + 10;   // 报错
```

`const`定义常量与使用`let` 定义的变量相似：

- 二者都是块级作用域
- 都不能和它所在作用域内的其他变量或函数拥有相同的名称

两者还有以下两点区别：

- `const`声明的常量必须初始化，而`let`声明的变量不用
- const 定义常量的值不能通过再赋值修改，也不能再次声明。而 let 定义的变量值可以修改。

```
var x = 10;
// 这里输出 x 为 10
{ 
    const x = 2;
    // 这里输出 x 为 2
}
// 这里输出 x 为 10
```

const 声明的常量必须初始化：

```
// 错误写法
const PI;
PI = 3.14159265359;

// 正确写法
const PI = 3.14159265359;
```

并非真正的常量

const 的本质: const 定义的变量并非常量，并非不可变，它定义了一个常量引用一个值。使用 const 定义的对象或者数组，其实是可变的。下面的代码并不会报错：

```
// 创建常量对象
const car = {type:"Fiat", model:"500", color:"white"};
 
// 修改属性:
car.color = "red";
 
// 添加属性
car.owner = "Johnson";
```

但不能对常量对象重新赋值。

重置变量

使用 **var** 关键字声明的变量在任何地方都可以修改：

实例

var x = 2;    //  合法 var x = 3;    //  合法 x = 4;        //  合法

在相同的作用域或块级作用域中，不能使用 **const** 关键字来重置 **var** 和 **let**关键字声明的变量:

```
var x = 2;         // 合法
const x = 2;       // 不合法
{
    let x = 2;     // 合法
    const x = 2;   // 不合法
}
```

在相同的作用域或块级作用域中，不能使用 **const** 关键字来重置 **const** 关键字声明的变量:

```
const x = 2;       // 合法
const x = 3;       // 不合法
x = 3;             // 不合法
var x = 3;         // 不合法
let x = 3;         // 不合法

{
    const x = 2;   // 合法
    const x = 3;   // 不合法
    x = 3;         // 不合法
    var x = 3;     // 不合法
    let x = 3;     // 不合法
}
```

**const** 关键字在不同作用域，或不同块级作用域中是可以重新声明赋值的:

```
const x = 2;       // 合法

{
    const x = 3;   // 合法
}

{
    const x = 4;   // 合法
}
```

### 变量提升

JavaScript var 关键字定义的变量可以在使用后声明，也就是变量可以先使用再声明。

```
carName = "Volvo";   
// 这里可以使用 carName 变量 var carName;
```

const 关键字定义的变量则不可以在使用后声明，也就是变量需要先声明再使用。

```
carName = "Volvo";   // 在这里不可以使用 carName 变量
const carName = "Volvo";
```

























- ❗ 变量解构赋值

解构赋值是对赋值运算符的扩展。

他是一种针对数组或者对象进行模式匹配，然后对其中的变量进行赋值。

在代码书写上简洁且易读，语义更加清晰明了；也方便了复杂对象中数据字段获取。

------

## 解构模型

在解构中，有下面两部分参与：

解构的源，解构赋值表达式的右边部分。解构的目标，解构赋值表达式的左边部分。

------

#### 数组模型的解构（Array）

基本、可嵌套、可忽略、不完全解构、剩余运算符、字符串等

结构默认值：

```
let [a = 2] = [undefined]; // a = 2
```

当解构模式有匹配结果，且匹配结果是 undefined 时，会触发默认值作为返回结果。

l

```
let [a = 3, b = a] = [];        // a = 3, b = 3
let [a = 3, b = a] = [1];        // a = 1, b = 1
let [a = 3, b = a] = [1, 2];     // a = 1, b = 2
```

a 与 b 匹配结果为 undefined ，触发默认值：**a = 3; b = a =3**

- a 正常解构赋值，匹配结果：a = 1，b 匹配结果 undefined ，触发默认值：**b = a =1**
- a 与 b 正常解构赋值，匹配结果：**a = 1，b = 2**

#### 对象模型的解构（Object）

**基本**

let { foo, bar } = { foo: 'aaa', bar: 'bbb' }; // foo = 'aaa' // bar = 'bbb'  let { baz : foo } = { baz : 'ddd' }; // foo = 'ddd'

**可嵌套可忽略**

let obj = {p: ['hello', {y: 'world'}] }; let {p: [x, { y }] } = obj; // x = 'hello' // y = 'world' let obj = {p: ['hello', {y: 'world'}] }; let {p: [x, {  }] } = obj; // x = 'hello'

**不完全解构**

```
let obj = {p: [{y: 'world'}] };
let {p: [{ y }, x ] } = obj; 
// x = undefined // y = 'world'
```

**剩余运算符**

```
let {a, b, ...rest} = {a: 10, b: 20, c: 30, d: 40};
// a = 10 // b = 20 // rest = {c: 30, d: 40}
```

**解构默认值**

```
let {a = 10, b = 5} = {a: 3}; // a = 3; b = 5; let {a: aa = 10, b: bb = 5} = {a: 3}; // aa = 3; bb = 5;


```



## ❗❗ 箭头函数

箭头函数提供了一种更加简洁的函数书写方式。基本语法是：

```
参数 => 函数体
```

基本用法：

```
var f = v => v; 
//等价于 
var f = function(a){ return a; }
f(1);  //1
```

当箭头函数没有参数或者有多个参数，要用 **()** 括起来。

```
var f = (a,b) => a+b; f(6,2);  //8
```

当箭头函数函数体有多行语句，用 **{}** 包裹起来，表示代码块，当只有一行语句，并且需要返回结果时，可以省略 **{}** , 结果会自动返回。

```
var f = (a,b) => { 
let result = a+b;
return result; 
} 
f(6,2);  // 8
```

当箭头函数要返回对象的时候，为了区分于代码块，要用 () 将对象包裹起来

// 报错

```
var f = (id,name) => {id: id, name: name};
f(6,2);  // SyntaxError: Unexpected token :
 
// 不报错
var f = (id,name) => ({id: id, name: name});
f(6,2);  // {id: 6, name: 2}
注意点：没有 this、super、arguments 和 new.target 绑定。

var func = () => {
  // 箭头函数里面没有 this 对象，
  // 此时的 this 是外层的 this 对象，即 Window 
  console.log(this)
}
func(55)  // Window 
 
var func = () => {    
  console.log(arguments)
}
func(55);  // ReferenceError: arguments is not defined
```

箭头函数体中的 this 对象，是定义函数时的对象，而不是使用函数时的对象。

```
function fn(){
  setTimeout(()=>{
    // 定义时，this 绑定的是 fn 中的 this 对象
    console.log(this.a);
  },0)
}
var a = 20;
// fn 的 this 对象为 {a: 18}
fn.call({a: 18});  // 18
```

不可以作为构造函数，也就是不能使用 new 命令，否则会报错



适合使用的场景
可用于回调函数，经常看到 var self = this 这样的代码，为了将外部 this 传递到回调函数中，那么有了箭头函数，就不需要这样做了，直接使用 this 就行。

```
// 回调函数
var Person = {
    'age': 18,
    'sayHello': function () {
      setTimeout(function () {
        console.log(this.age);
      });
    }
};
var age = 20;
Person.sayHello();  // 20
 
var Person1 = {
    'age': 18,
    'sayHello': function () {
      setTimeout(()=>{
        console.log(this.age);
      });
    }
};
var age = 20;
Person1.sayHello();  // 18

```

所以，当我们需要维护一个 this 上下文的时候，就可以使用箭头函数。

不适合使用的场景:
定义函数的方法，且该方法中包含 this

```
var Person = {
    'age': 18,
    'sayHello': ()=>{
        console.log(this.age);
      }
};
var age = 20;
Person.sayHello();  // 20
// 此时 this 指向的是全局对象
 
var Person1 = {
    'age': 18,
    'sayHello': function () {
        console.log(this.age);
    }
};
var age = 20;
Person1.sayHello();   // 18
// 此时的 this 指向 Person1 对象
需要动态 this 的时候

var button = document.getElementById('userClick');
button.addEventListener('click', () => {
     this.classList.toggle('on');
});
```

button 的监听函数是箭头函数，所以监听函数里面的 this 指向的是定义的时候外层的 this 对象，即 Window，导致无法操作到被点击的按钮对象。

- 
- 
- Symbol

#### 基本用法

Symbol 函数栈不能用 new 命令，因为 Symbol 是原始数据类型，不是对象。可以接受一个字符串作为参数，为新创建的 Symbol 提供描述，用来显示在控制台或者作为字符串的时候使用，便于区分。

```
let sy = Symbol("KK"); 
console.log(sy);   // Symbol(KK)
typeof(sy);        // "symbol" 
// 相同参数 Symbol() 返回的值不相等 
let sy1 = Symbol("kk");  sy === sy1;       // false
```

#### 使用场景

##### 作为属性名

**用法**

由于每一个 Symbol 的值都是不相等的，所以 Symbol 作为对象的属性名，可以保证属性不重名。

l

```
let sy = Symbol("key1"); 
// 写法1
let syObject = {};
syObject[sy] = "kk"; 
console.log(syObject);    // {Symbol(key1): 
"kk"
}  
// 写法2 
let syObject = { 
[sy]: "kk" }; console.log(syObject);    // {Symbol(key1): "kk"
}  
// 写法3 
let syObject = {}; 
Object.defineProperty(syObject, sy, {value: "kk"}); console.log(syObject);   // {Symbol(key1): "kk"}
```

Symbol 作为对象属性名时不能用.运算符，要用方括号。因为.运算符后面是字符串，所以取到的是字符串 sy 属性，而不是 Symbol 值 sy 属性。

```
let syObject = {};
syObject[sy] = "kk";  
syObject[sy];  // "kk"
syObject.sy;   // undefined
```



##### 注意点:

```
Symbol 值作为属性名时，该属性是公有属性不是私有属性，可以在类的外部访问。但是不会出现在 for...in 、 for...of 的循环中，也不会被 Object.keys() 、 Object.getOwnPropertyNames() 返回。如果要读取到一个对象的 Symbol 属性，可以通过 Object.getOwnPropertySymbols() 和 Reflect.ownKeys() 取到。
```



```
let syObject = {}; 
syObject[sy] = "kk"; 
console.log(syObject); 
for (let i in syObject) {  console.log(i); } 
// 无输出 
Object.keys(syObject);                   // [] Object.getOwnPropertySymbols(syObject);  
// [Symbol(key1)]
Reflect.ownKeys(syObject);       // [Symbol(key1)]
```

### 定义常量

在 ES5 使用字符串表示常量。例如：

```
const COLOR_RED = "red";
const COLOR_YELLOW = "yellow";
const COLOR_BLUE = "blue";
```

但是用字符串不能保证常量是独特的，这样会引起一些问题：

```
const COLOR_RED = "red";
const COLOR_YELLOW = "yellow"; 
const COLOR_BLUE = "blue"; 
const MY_BLUE = "blue";  
function ColorException(message) { 
this.message = message;  
this.name = "ColorException";
}  function getConstantName(color) {   
switch (color) {       
case COLOR_RED :          
return "COLOR_RED";       
case COLOR_YELLOW :           
return "COLOR_YELLOW ";       
case COLOR_BLUE:            
return "COLOR_BLUE";      
case MY_BLUE:          
return "MY_BLUE";              
default:           
throw new ColorException("Can't find this color");    
} 
}  
try {      
var color = "green"; // green 引发异常   
var colorName = getConstantName(color); } catch (e) {   var colorName = "unknown";  
console.log(e.message, e.name); // 传递异常对象到错误处理 }
```

但是使用 Symbol 定义常量，这样就可以保证这一组常量的值都不相等。用 Symbol 来修改上面的例子。

```
const COLOR_RED = Symbol("red");
const COLOR_YELLOW = Symbol("yellow"); 
const COLOR_BLUE = Symbol("blue");  
function ColorException(message) {  
this.message = message;  
this.name = "ColorException";
} function getConstantName(color) {    
switch (color) {      
case COLOR_RED :          
return "COLOR_RED";       
case COLOR_YELLOW :       
return "COLOR_YELLOW ";     
case COLOR_BLUE:          
return "COLOR_BLUE";      
default:            
throw new ColorException("Can't find this color");   
} 
}  
try {     
var color = "green"; // green 引发异常 
var colorName = getConstantName(color);
} catch (e) {  
var colorName = "unknown";  
console.log(e.message, e.name); // 传递异常对象到错误处理 }
```

Symbol 的值是唯一的，所以不会出现相同值得常量，即可以保证 switch 按照代码预想的方式执行。

### Symbol.for()

Symbol.for() 类似单例模式，首先会在全局搜索被登记的 Symbol 中是否有该字符串参数作为名称的 Symbol 值，如果有即返回该 Symbol 值，若没有则新建并返回一个以该字符串参数为名称的 Symbol 值，并登记在全局环境中供搜索。

```
let yellow = Symbol("Yellow");
let yellow1 = Symbol.for("Yellow"); 
yellow === yellow1;      // false  
let yellow2 = Symbol.for("Yellow"); 
yellow1 === yellow2;     // true
```



### Symbol.keyFor()

Symbol.keyFor() 返回一个已登记的 Symbol 类型值的 key ，用来检测该字符串参数作为名称的 Symbol 值是否已被登记。

```
let yellow1 = Symbol.for("Yellow"); Symbol.keyFor(yellow1);    // "Yellow"
```





## Set 和 Map 数据结构

### Map 对象

Map 对象保存键值对。任何值(对象或者原始值) 都可以作为一个键或一个值。

### Maps 和 Objects 的区别

- 一个 Object 的键只能是字符串或者 Symbols，但一个 Map 的键可以是任意值。
- Map 中的键值是有序的（FIFO 原则），而添加到对象中的键则不是。
- Map 的键值对个数可以从 size 属性获取，而 Object 的键值对个数只能手动计算。
- Object 都有自己的原型，原型链上的键名有可能和你自己在对象上的设置的键名产生冲突。

### Map 中的 key

**key 是字符串*、对象、函数、NaN.

#### Map 的迭代

对 Map 进行遍历，以下两个最高级。

```
for...of
var myMap = new Map();
myMap.set(0, "zero");
myMap.set(1, "one");
 
// 将会显示两个 log。 一个是 "0 = zero" 另一个是 "1 = one"
for (var [key, value] of myMap) {
  console.log(key + " = " + value);
}
for (var [key, value] of myMap.entries()) {
  console.log(key + " = " + value);
}
/* 这个 entries 方法返回一个新的 Iterator 对象，它按插入顺序包含了 Map 对象中每个元素的 [key, value] 数组。 */
 
// 将会显示两个log。 一个是 "0" 另一个是 "1"
for (var key of myMap.keys()) {
  console.log(key);
}
/* 这个 keys 方法返回一个新的 Iterator 对象， 它按插入顺序包含了 Map 对象中每个元素的键。 */
 
// 将会显示两个log。 一个是 "zero" 另一个是 "one"
for (var value of myMap.values()) {
  console.log(value);
}
/* 这个 values 方法返回一个新的 Iterator 对象，它按插入顺序包含了 Map 对象中每个元素的值。 */

```

forEach()

```
var myMap = new Map();
myMap.set(0, "zero");
myMap.set(1, "one");
 
// 将会显示两个 logs。 一个是 "0 = zero" 另一个是 "1 = one"
myMap.forEach(function(value, key) {
  console.log(key + " = " + value);
}, myMap)
```

### Map 对象的操作

**Map 与 Array的转换**

```
var kvArray = [["key1", "value1"], ["key2", "value2"]];  // Map 构造函数可以将一个 二维 键值对数组转换成一个 Map 对象 
var myMap = new Map(kvArray); 
// 使用 Array.from 函数可以将一个 Map 对象转换成一个二维键值对数组 
var outArray = Array.from(myMap);
```

**Map 的克隆**

```
var myMap1 = new Map([["key1", "value1"], ["key2", "value2"]]); 
var myMap2 = new Map(myMap1); 
console.log(original === clone); 
// 打印 false。 Map 对象构造函数生成实例，迭代出新的对象。
```

**Map 的合并**

```
var first = new Map([[1, 'one'], [2, 'two'], [3, 'three'],]); 
var second = new Map([[1, 'uno'], [2, 'dos']]); 
// 合并两个 Map 对象时，如果有重复的键值，则后面的会覆盖前面的，对应值即 uno，dos， three var merged = new Map([...first, ...second]);
```

## Set 对象

Set 对象允许你存储任何类型的唯一值，无论是原始值或者是对象引用。

### Set 中的特殊值

Set 对象存储的值总是唯一的，所以需要判断两个值是否恒等。有几个特殊值需要特殊对待：

- +0 与 -0 在存储判断唯一性的时候是恒等的，所以不重复；
- undefined 与 undefined 是恒等的，所以不重复；
- NaN 与 NaN 是不恒等的，但是在 Set 中只能存一个，不重复。

```
let mySet = new Set();
 
mySet.add(1); // Set(1) {1}
mySet.add(5); // Set(2) {1, 5}
mySet.add(5); // Set(2) {1, 5} 这里体现了值的唯一性
mySet.add("some text"); 
// Set(3) {1, 5, "some text"} 这里体现了类型的多样性
var o = {a: 1, b: 2}; 
mySet.add(o);
mySet.add({a: 1, b: 2}); 
// Set(5) {1, 5, "some text", {…}, {…}} 
// 这里体现了对象之间引用不同不恒等，即使值相同，Set 也能存储
```

类型转换
Array

```
// Array 转 Set
var mySet = new Set(["value1", "value2", "value3"]);
// 用...操作符，将 Set 转 Array
var myArray = [...mySet];
String
// String 转 Set
var mySet = new Set('hello');  // Set(4) {"h", "e", "l", "o"}
// 注：Set 中 toString 方法是不能将 Set 转换成 String
```

### Set 对象作用

**数组去重**（[...myset]）、并集(union)、交集(intersect)、差集(difference)

```
var mySet = new Set([1, 2, 3, 4, 4]);
[...mySet]; // [1, 2, 3, 4]
```

```
var a = new Set([1, 2, 3]);
var b = new Set([4, 3, 2]);
var intersect = new Set([...a].filter(x => b.has(x))); // {2, 3}
```



## Proxy 和 Reflect（目前阶段了解）

## 基本用法

### Proxy

一个 Proxy 对象由两个部分组成： target 、 handler 。在通过 Proxy 构造函数生成实例对象时，需要提供这两个参数。 target 即目标对象， handler 是一个对象，声明了代理 target 的指定行为。

```
let target = {
    name: 'Tom',
    age: 24
}
let handler = {
    get: function(target, key) {
        console.log('getting '+key);
        return target[key]; // 不是target.key
    },
    set: function(target, key, value) {
        console.log('setting '+key);
        target[key] = value;
    }
}
let proxy = new Proxy(target, handler)
proxy.name     // 实际执行 handler.get
proxy.age = 25 // 实际执行 handler.set
// getting name
// setting age
// 25
 
// target 可以为空对象
let targetEpt = {}
let proxyEpt = new Proxy(targetEpt, handler)
// 调用 get 方法，此时目标对象为空，没有 name 属性
proxyEpt.name // getting name
// 调用 set 方法，向目标对象中添加了 name 属性
proxyEpt.name = 'Tom'
// setting name
// "Tom"
// 再次调用 get ，此时已经存在 name 属性
proxyEpt.name
// getting name
// "Tom"
 
// 通过构造函数新建实例时其实是对目标对象进行了浅拷贝，因此目标对象与代理对象会互相
// 影响
targetEpt
// {name: "Tom"}
 
// handler 对象也可以为空，相当于不设置拦截操作，直接访问目标对象
let targetEmpty = {}
let proxyEmpty = new Proxy(targetEmpty,{})
proxyEmpty.name = "Tom"
targetEmpty // {name: "Tom"}
```

实例方法

```
get(target, propKey, receiver)
```

#### apply(target, ctx, args)

用于拦截函数的调用、call 和 reply 操作。target 表示目标对象，ctx 表示目标对象上下文，args 表示目标对象的参数数组。

```
has(target, propKey)
```

用于拦截 HasProperty 操作，即在判断 target 对象是否存在 propKey 属性时，会被这个方法拦截。此方法不判断一个属性是对象自身的属性，还是继承的属性。

```
let  handler = {
    has: function(target, propKey){
        console.log("handle has");
        return propKey in target;
    }
}
let exam = {name: "Tom"}
let proxy = new Proxy(exam, handler)
'name' in proxy
// handle has
// true
```

注意：此方法不拦截 for ... in 循环。

```
construct(target, args)
```

用于拦截 new 命令。返回值必须为对象。

```
let handler = {
    construct: function (target, args, newTarget) {
        console.log('handle construct')
        return Reflect.construct(target, args, newTarget)  
    }
}
class Exam { 
    constructor (name) {  
        this.name = name 
    }
}
let ExamProxy = new Proxy(Exam, handler)
let proxyObj = new ExamProxy('Tom')
console.log(proxyObj)
// handle construct
// exam {name: "Tom"}
```

```
deleteProperty(target, propKey)
```

用于拦截 delete 操作，如果这个方法抛出错误或者返回 false ，propKey 属性就无法被 delete 命令删除。

```
defineProperty(target, propKey, propDesc)
```

用于拦截 Object.definePro若目标对象不可扩展，增加目标对象上不存在的属性会报错；若属性不可写或不可配置，则不能改变这些属性。

#### Reflect

Reflect 对象对某些方法的返回结果进行了修改，使其更合理。

Reflect 对象使用函数的方式实现了 Object 的命令式操作。

#### **静态方法**

```
Reflect.get(target, name, receiver)
```

```
Reflect.deleteProperty(obj, property)
```

是 delete obj[property] 的函数化，用于删除 obj 对象的 property 属性，返回值为 boolean。如果 obj 不是对象则会报错 TypeError。

```
Reflect.construct(obj, args)
```

等同于 new target(...args)。

```
Reflect.getPrototypeOf(obj)
```

用于读取 obj 的 _proto_ 属性。在 obj 不是对象时不会像 Object 一样把 obj 转为对象，而是会报错。

```
Reflect.setPrototypeOf(obj, newProto)
```

用于设置目标对象的 prototype。

```
Reflect.apply(func, thisArg, args)
```

等同于 Function.prototype.apply.call(func, thisArg, args) 。func 表示目标函数；thisArg 表示目标函数绑定的 this 对象；args 表示目标函数调用时传入的参数列表，可以是数组或类似数组的对象。若目标函数无法调用，会抛出 TypeError 。

```
Reflect.apply(Math.max, Math, [1, 3, 5, 3, 1]); // 5
```

```
Reflect.defineProperty(target, propertyKey, attributes)
```

```
Reflect.getOwnPropertyDescriptor(target, propertyKey)
```

用于得到 target 对象的 propertyKey 属性的描述对象。在 target 不是对象时，会抛出错误表示参数非法，不会将非对象转换为对象。

```
Reflect.isExtensible(target)
```

用于判断 target 对象是否可扩展。返回值为 boolean 。如果 target 参数不是对象，会抛出错误。

```
Reflect.preventExtensions(target)
```

用于让 target 对象变为不可扩展。如果 target 参数不是对象，会抛出错误。

```
Reflect.ownKeys(target)
```

用于返回 target 对象的所有属性，等同于 Object.getOwnPropertyNames 与Object.getOwnPropertySymbols 之和。







<未完待续>

- 
- 
- ❗❗ Promise & async / await 异步编程





- Generator 函数异步编程（目前阶段了解）
- ❗ Class类
- ❗ Module模块