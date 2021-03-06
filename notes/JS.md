# JavaScript

[TOC]

### Hello World

###### 书写位置

```html
<script type="text/javascript">
	alert("Hello World");
</script>
```

JS 要写在 HTML 中，因为JS 运行必须要有宿主环境，即浏览器

JS 要写在 Script 标签对中

###### alert() 语句

这是一个内置函数，用于在页面中弹出警告框

###### 控制台

程序的所有未捕获的错误，都会在控制台中输出，经常用于调试程序

`console.log()` 可用于向控制台输出数据

###### JS 特点

对换行、空格、缩进均不敏感

语句单行书写时后面可以不写分号，写在一行必须加分号

### 字面量

###### 数字的字面量

- 整数

  数字的字面量就是数字自己，不需要任何符号界定，JS 中数字的字面量有三种进制

  > 十进制：普通数字就是十进制
  >
  > 八进制：以 0、0o、0O 开头的都是八进制
  >
  > 十六进制：以 0x 开头的都是十六进制

- 小数

  小数的字面量是数学上的点，可以用 e 来表示乘以 10 的几次幂，十进制具有小数的字面量，八进制、十六进制没有

- 其他

  Infinity 表示无穷大，具有正负，例如 6/0 就是Infinity

  NaN 表示不是一个数，0/0 就返回 NaN

###### 字符串的字面量

字符串的字面量必须用单引号、双引号包裹起来，字符串被限定在同种引号之间

> 转义字符：\n 换行，\t Tab 缩进，可以用 `\` 来转义引号、斜杠本身等等

### 变量

变量与字面量不同，例如一个变量 a，它的含义不是字母 a，而是内部蕴含着不同的值

###### 定义

```js
var a;
```

通过 `var` 关键字可以定义一个变量，变量必须先声明，才能使用

###### 赋值

```js
var a;
a = 100;
```

使用等号可以对变量赋值，等号只表示赋值，没有其他含义

###### 标识符

由字母、下划线（_）、美元（$）符号、数字（0-9）组成，但不能以数字开头

###### 变量声明的提升

```js
a = 100;
var a;	//此语句会被提升到所有语句之前
console.log(a);
```

JS 会将定义变量语句自动提升到所有语句之前，仅提升定义，不提升赋值

###### 不写 var

```js
a = 100;
```

不写 var 定义的变量为全局变量，作用域不能控制

### 变量类型

###### 基本类型

number: 数字类型

string: 字符串类型

undefined: 变量未定义时的值

boolean: 布尔类型

null: null 类型

###### typeof 关键字

```js
var a = 100;
console.log(typeof a)
```

此关键字可以用于检测变量的类型

###### number 类型

JS 中所有的数字都是 number 类型：所有数字（不分正负、不分整浮、不分大小、不分进制）、Infinity、NaN

###### string 类型

用引号括起来的内容就是字符串类型

> JS 语言是动态数据类型，变量是什么类型，和定义的时候没有关系，它和具体赋值有关，它的变量类型是自动检测的

###### undefined 类型

变量只通过 var 定义，还没有赋值的时候它的值为 undefined ，它的类型也是 undefined 

###### 加号

加号是一个运算符，加号两边都是数字时，就是数学加法；两边不都是数字时，就是拼接字符串

### 变量类型转换

###### prompt("提示文本","默认值")

```js
prompt("请输入一个数字","50")
```

此语句用于弹出一个输入框，它接收到的所有东西都是字符串

###### parseInt()

可以将一个字符串转换为整数，也可用于将任何进制的数转换为十进制

parseInt() 不能转换时返回 NaN

###### parseFloat()

可以将一个字符串转换为浮点数

###### 数字转换为字符串

将一个数字与一个空字符串进行拼接，则数字自动转换为字符串

### 运算符

###### 数学运算符

> \+  \-  \*  /  %  

隐式转换，所有的带字符串的运算都会尽可能转为数字进行计算，加号除外

数学运算中，纯字符串、布尔值、null 都能够进行隐式转换

> null 会被转换为 0，true 为 1，false 为 0

不纯的字符串和 undefined 不能进行隐式转换，结果都是 NaN

> Math.pow(3,4)  
>
> Math.sqrt(81) 
>
> Math.random()	随机获取(0,1)之间的数

###### 关系运算符

> \>  \<  =  \>=  \<=  ==  !=  ===  !==

== 是相等判断，=== 是全等判断

> string 和 string 能够进行比较，比较的是字符编码顺序
>
> 与数字进行关系运算时，纯数字字符串、布尔值、null 会被隐式转换，null 为 0， true 为 1，false 为 0，注意 null 不能进行和 0 的相等判断
>
> NaN 不等于自己，不全等于自己

###### 逻辑运算符

> &&	||	!

###### 赋值运算符

> =  +=  -=  *=  /=  %=  ++  --

### 条件分支语句

###### if() ... else if() ... else

###### switch case

###### 三元运算符(? : )

### 循环语句

###### for 循环

###### do...while()

###### while()

###### continue 和 break

### 函数

###### 函数定义

```js
function add() {
    alert("add()方法");
}
```

通过 function 关键字可定义函数

###### 函数调用

```js
add();
```

调用 add 方法，函数必须先定义在调用

###### 带参函数

```js
function add(a,b) {
    alert(a + b);
}

add(5,7);
```

定义函数的时候，不需要指定参数类型，调用时传入什么类型就是什么类型

调用时传入的参数个数和定义个数不一致不会报错，例如定义需要两个参数，调用时只传入一个，则第二个会被隐式定义，值为 undefined，调用时传入多个则只有前两个被使用，其他的被忽略

###### 函数返回值

```js
function add(a,b) {
    return a+b;
}
```

函数可以通过 return 语句来返回值，只能有唯一的 return，if 除外

###### 函数表达式

```js
var subtract = function(a,b) {
    return a-b;
}
```

这种函数叫匿名函数，为了调用，它直接被赋值给一个变量

###### 函数声明的提升

JS 在执行前，会有一个预解析过程，把所有函数定义都提升到最开头，函数表达式不会被提升，如果遇见标识符冲突，如一个标识符既是函数的名字，又是变量的名字，这个标识符给函数

函数声明的提升，是强制提升的，即使用 if 语句，也会提升

###### 函数是引用类型

JS 中有基本类型，也有引用类型，引用类型有很多种：object、function、array、RegExp、Math、Date

函数就是 function 类型，是引用类型的一种

基本类型保存值，引用类型保存地址

###### 同名函数

JS 中实参个数和形参个数可以不一样，JS 没有重载概念，只要存在同名的函数，后写的就会覆盖先写的

###### arguments

JS 每一个函数内部，都有一个 arguments 类数组对象，这个对象涵盖了所有实参

```js
function add(a,b){ ... }

add(5,6,7,8)	//arguments[0]=5,arguments[1]=6,arguments[2]=7
```

arguments 可以用来模拟函数的重载

```js
function add(a,b) {
    switch(arguments.length){
    	case 1:
    		return a;
            break;
    	case 2:
            return a+b;
            break;
    }
}
```

### 作用域

###### 变量作用域

定义在 function 内部的变量叫做局部变量，仅在函数内有效

定义在全局范围内的，即没写在函数内的变量，叫做全局变量，全局范围内可以使用

###### 作用域链

当遇见一个变量时，JS 引擎会在其所在的作用域依次向外层查找，查找会在找到第一个匹配的标识符的时候停止，如果有同名的变量，那么会发生遮蔽效应，即外层的变量会被第一个找到的变量遮蔽

###### 不写 var 的变量

JS 机制如果遇见一个标识符，从来没有被 var 定义过，并且还赋值了，那么 JS 会自动在全局范围内定义这个变量

###### 函数参数

函数的参数会被默认定义为这个函数的局部变量

###### 全局变量

全局变量一般用于两个功能

1. 通信，如两个函数共同操作一个变量
2. 累加，重复调用函数的时候，不会重置

###### 函数作用域

定义在函数内部的函数只能在其函数内部使用，函数外部无法访问

### 闭包

###### 概述

一个函数可以把它自己内部的语句，和自己声明时所处的作用域一起封装成一个密闭的环境，这就是“闭包”

每个函数都是闭包，每个函数天生都能够记忆自己定义时所处的作用域环境，可通过将函数挪到别的作用域观察闭包现象

闭包一般用来防止隐患

###### 闭包性质

每次重新引用函数的时候，闭包是全新的

无论在何处访问，它总是能访问它定义时所处作用域的全部变量

### 数组

###### 概述

```js
var arr = [1,5,8,7,6];
```

数组是一个有序的数据集合，它的字面量是方括号

数组中可以不保存相同类型的数据，但实际中一般将相同的数据保存到数组中

数组具有 `length` 属性

###### 数组遍历

```js
for(var i=0; i<arr.length-1; i++) {
    alert(arr[i]);
}
```

可通过 for 循环遍历数组

###### 数组类型

数组是一个引用类型

```js
var a = [1,2,3];
alert(typeof a);	//object
```

保存数组的变量，实际保存的是数组内存地址

```js
var a = [1,2,3];
var b = [1,2,3];
console.log(a == b);	//false，比较地址，两者地址不一样
```

如果数组 a 存储的是基本类型，则 `b=a` 把 a 的值赋值一份给 b，如果数组 a 里面存储的是引用类型，则 b 指向 a 现在的位置，a 不再是赋值一份给 b

### 数组常见方法

###### 头尾操作

push()

```js
var arr = [1,12,35];
arr.push(5,785,5);
```

在数组末尾添加项目

> pop()	删除末尾元素，并返回删除元素，只能删除一项
>
> unshift()	在头部插入元素
>
> shift()	删除头部元素

###### 合并拆分

concat()

```js
var arr1 = [1,5,8];
var arr2 = [57,95,85];
arr1.concat(arr2);
arr1.concat(arr2,8,[5,8,8])
```

将两个数组合并为一个新数组返回，原数组本身不改变

slice()

```js
var arr1 = ["我","你","他","它","她"]；
var arr2 = arr1.slice(1,3)；	//截取下标为1、2的作为新数组返回
var arr3 = arr1.slice(4);	//从4开始截取到末尾
```

`arr.slice(start,end)` 返回一个新数组，包含从 start 到 end 的元素，不包含 end

###### 多功能 splice()

splice() 不返回新数组，直接更改原数组，可用于插入、删除、替换数组中的数

```js
var arr = ["a","b","c","d","e","f","g"];
arr.splice(1,2,"x","y","z")	//替换从索引1开始的连续两项为 x、y、z
arr.splice(3,0,"m","n")	//在索引为3的项前面插入 m、n
arr.splice(-3);	//删除数组最后三项
```

###### 逆序 reverse()

```js
var arr = [1,2,3,4];
arr.reverse();	//改变原数组
```

此方法用于将数组倒置

###### 排序 sort()

sort() 函数默认按照字符顺序排序，隐式将数字转为 string，比较字符编码顺序

sort() 中可以传入参数，这个参数为一个函数

```js
var arr = [1,22,55,5,4,87,3];
arr.sort(
    function(a,b) {
        if(a<b)
            return -1;
        else if(a>b)
            return 1;
        else
            return 0;
    }
)
```

###### 转为字符串

```js
var arr = [1,2,3,4,5];
var str = arr.join(";");	//1;2;3;4;5
```

`arr.join("分隔符")` 用特定分隔符将数组转换为字符串，不传入分隔符默认使用逗号

### 字符串常见属性方法

###### length

返回字符串长度

###### charAt()	

```js
var str = "abcdefg";
var res = str.charAt(0);	//a
```

返回指定位置字符

###### concat()

```js
var str1 = "haha";
var str2 = "xixi";
str1.concat(str2);
```

连接字符串

###### indexOf()

```js
var str = "beautiful"；
str.indexOf("f");	//6
```

检索字符串

###### replace()

```js
var str = "abcdefg";
str.replace("a","0");
```

替换字符串

###### slice()

```js
"我是真的很不错".slice(-5,-2);	//真的
```

提取字符串

###### split()

拆分字符串为数组

###### substr(start,length)

截取子串

###### substring(start,end)

###### toLowerCase()

转换为小写

###### toUpperCase()

转换为大写

### 正则表达式

###### 创建正则表达式

```js
//使用正则表达式字面量
var re1 = /abc/;
//调用 RegExp 对象的构造函数
var re2 = new RegExp("abc");
```

可通过以上两种方式创建正则表达式

###### spilt()

可通过正则表达时切割字符串

``` js
var str = "a    b    c";
str.spilt(/\s+/);
```

###### serach()

用来寻找字符或字符串在父字符串中的位置，可以传递字符、字符串、正则表达式

```js
var str = "abcde";
str.serach('cd');
str.serach(/cd/);
```

类数组：融合了数组和对象的一个对象，可以使用数组的方法、属性，也可使用对象的方法、属性

正则表达式是一个严格模式，不能乱添加空格

###### match()

在父字符串中寻找匹配字符串，字符串方法，参数为字符串或匹配的规则

```js
var str = 'abbaccadddaefkaddddeakf';
str.match(/b+/g);
str.match('bb');
```

###### replace()

替换父字符串中匹配的字符串，接受两个参数，一个是匹配的字符串，可以是字符串也可以是正则表达式；另一个是替换的字符串，可以是字符串也可以是函数，函数要有返回值

```js
var str="www.baidu.com";
str.replace(/baidu\.com/,'iqiyi.cn');
str.replace(/baidu\.com/,function(){
    return 'iqiyi.cn';
});
```

###### exec

它是正则对象的方法，对正则对象直接调用即可，它在字符串中匹配符合正则规则的字符串

```js
var reg = new RegExp("abc","g");
var str = "aabaabcccbabaaccabacbcabccc";
reg.exec(str);
```

###### test

正则对象的方法，它表示该字符串是否匹配正则规则

```js
var reg = /hello/;
var str = 'hello world';
reg.test(str);	//true
```

### 正则表达式语法

###### 特殊字符

正则表达式由普通字符和特殊字符（元字符）组成

普通字符：字母，数字，_ 等

特殊字符： ()  []  {}  ^  $  *  ?  \  |  +  .

普通字符可直接使用，特殊字符转义后才能使用

```js
// 匹配 \a
var reg = /\\a/;
// 匹配 ^c
var reg = /\^c/;
```

###### 预定义特殊字符

\t: 制表符	\n:回车符	\f:换页符	\b:回退

###### 字符集

JS 的正则表达式有四类字符集

简单类：[abCD123]，表示这几个字母数字组成的一个集合

范围类：[A-Z]，大写字母集合；[a-z]，小写字母集合；[0-9]，数字集合

负向类：\[^abc]，表示不包含 abc 的任意字符集  

组合类：[a-zA-Z0-9]，表示大小写字母以及数字的结合

###### 分界

字符串是有边界的

```js
var reg = /^abc/;	//匹配以abc开头的字符
var reg2 = /abc$/;	//匹配以abc结尾的字符
```

`^` 表示开头，`$` 表示结尾

单词的分界，`\b` 表示 [a-zA-Z_0-9] 之外的单词分割符，`\B` 表示非单词分隔符

###### 预定义类

.	\[^\n\r]			 除了换行和回车之外的字符

\d     [0-9]	    		数字字符

\D     \[^0-9]	 		非数字字符

\s      [\t\n\x0B\f\r]	    空白字符

\S      \[^\t\n\x0B\f\r]	  非空白字符

\w     [a-zA-Z_0-9]	       单词字符

\W     \[^a-zA-Z_0-9]	    非单词字符

###### 量词

？	出现一次或零次

\*	出现零次或多次

\+	出现一次或多次

{n}	对应零次或 n 次

{n,m}	至少出现 n 次但不超过 m 次

{n,}	至少出现 n 次

###### 修饰词

g	表示全局匹配

i	表示忽略大小写

m	表示多行匹配

###### 其他

[\u4e00-\u9fa5] 表示中文集

| 表示或

###### 分组

### IIFE(immediately-invoked function expression)

即时调用函数表达式，即一个函数，在定义的时候就调用它

```js
(function(a,b){
    return a+b;
})(5,6);
```

这种方式定义的函数，名字无效，其他地方不能调用

### 数组闭包

以下现象就是因为每个函数在定义时都产生了闭包

```js
var arr = [];
for(var i=0; i<=10; i++) {
    arr[i] = function() {
        alert(i);
    }
}
arr[3]();	//11	
arr[6]();	//11
arr[8]();	//11
```

解决方案，使用 IIFE，因为 IIFE 里面的作用域时隔离的

```js
for(var i=0; i<=10; i++) {
    (function(m){
        arr[m] = function() {
            alert(m);
        }
    })(i);
}
```

### DOM(document object model)

DOM 描绘了一个层次化的节点树，允许开发人员添加、删除和修改页面的某一部分，通过 JS 操作 HTML，就是在操作节点

###### 得到元素

最基本的得到元素的方法有两个，这两个方法得到元素是所有浏览器都兼容的

> document.getElementById()

通过 Id 得到一个元素

> document.getElementsByTagName()

通过标签名得到元素组，它返回一个结果数组，就算只有一个元素也是数组

其他得到元素方法，这些方法不是所有浏览器都兼容的

> document.getElementsByClassName()	通过类名得到元素
>
> document.querySelector()	通过选择器得到元素

document 对象表示文档，即整个页面

###### 更改属性

可通过 `点语法` `setAttribute()` `getAttribute()` 更改属性

```html
<img src="i.jpg" id="img1"/>
<script>
    var oImg = document.getElementById("img1");
	oImg.src = "2.jpg";
    oImg.setAttribute("src","2.jpg");
</script>
```

要通过点语法更换一个元素的 class 属性，需使用className，class 是保留字，还有一些属性也需要避讳

> for 写为 htmlFor
>
> rowspan 写为 rowSpan
>
> colspan 写为 colSpan

自定义的属性不能通过点语法得到，但可以通过 setAttribute 得到

行内样式通过点语法的到一个样式对象，但通过 getAttribute 得到的是字符串

getAttrbute 获得属性时不需要避讳关键字

点语法效率远高于 getAttribute、setAtrribute

###### 操作元素样式

通过点语法 `.style` 可以得到行内样式的封装，不能得到内嵌、外联样式

```html
<div id="div1" style="border: 1px solid red"></div>
<script>
	var oDiv = document.getElementById("div1");
    oDiv.style.border = "5px dashed black";
</script>
```

通过 `Element.style.css` 样式名可以得到某一样式，所有 css 连字符的样式，都要转换为驼峰形式 ，通过这样方式操作样式读、设都在行内

> 信号量(semaphor)思维模式：信号量不用添加行内样式

###### 事件监听

> ![DOM event](../images/DOM event.png)

###### 批量添加事件

给页面上所有 p 添加 click 事件

```js
var oPs = document.getElementsByTagName("p");
for(var i=0; i<oPs.length; i++) {
    oPs[i].onclick = function(){
        alert(i);	//点击每个 p 都会弹出 length
    }
}
```

这种 for 循环添加监听语句会出现闭包

解决方案

```js
var oPs = document.getElementsByTagName("p");
for(var i=0; i<oPs.length; i++) {
    (function(m){
    	oPs[m].onclick = function(){
        	alert(m);
    	} 
    })(i);
}
```

```js
var oPs = document.getElementsByTagName("p");
for(var i=0; i<oPs.length; i++) {
    oPs[i].idx = i;
    oPs[i].onclick = function(){
        alert(this.idx);
    } 
}
```

###### 对应和排他

### 计算后样式

###### 高级浏览器

> window.getComputedStyle(oDiv).getPropertyValue("border-style")
>
> getComputedStyle(oDiv).getPropertyValue("border-style")
>
> getComputedStyle(oDiv)["border-style"]

getPropertyValue 接收 css 属性名称，不用驼峰式名称

###### 低级浏览器(IE 6、7、8)

它们不兼容 `getComputedStyle().getPropertyValue()` ，只能使用另一套写法，使用 `currentStyle` 属性，需要使用驼峰形式

> oDiv.currentStyle.borderStyle
>
> oDiv.currentStyle["barderStyle"]

###### 能力检测

为了让所有浏览器兼容，需要根据浏览器版本执行不同语句，可以通过能力检测完成，就不用在判断浏览器版本

```js
if(window.getComputedStyle){
    getComputedStyle(oDiv)["padding-left"];
}else{
    oDiv.currentStyle.paddingLeft;
}
```

### 快捷位置和尺寸

> ele.offsetLeft
>
> ele.offsetTop
>
> ele.offsetWidth
>
> ele.offsetHeight
>
> ele.clientWidth
>
> ele.clientHeight

###### offsetLeft 和 offsetTop

这两个属性不是所有浏览器兼容

一个元素的 offsetLeft 值，就是这个元素左边框外，到自己的 offsetParent 对象的左边框内的距离

offsetParent：无论自己是否定位，自己的祖先元素中，离自己最近的已经定位的元素，没有任何盒子定位，那么 offsetParent 对象就是 body

> IE 6、7：如果自己没有定位属性，那么自己的 offsetParent 对象就是自己的祖先元素离自己最近的有 width 或者有 height 的元素；如果自己有定位，那么 offset 就是离自己最近的有定位祖先元素
>
> IE 8：无论自己是否定位，offsetParent 就是离自己最近的已定位祖先元素，但是 offsetLeft 会算到父元素边框外部，即多算一条边

###### offsetWidth 和 offsetHeight

这两个属性所有浏览器兼容，它们是盒子自己的属性

offsetWidth 的值就是：width + 左右 padding + 左右 border

如果盒子没有宽度，浏览器把 px 当做 offsetWidth

如果盒子没有高度，用文字撑的，浏览器把 px 当做 offsetHeight

###### clientWidth 和 clientHeight

clientWidth 的值为：width + 左右 padding

### 运动

###### 定时器

```js
setInterval(function(){
    alert(new Date().getSeconds());
},1000)
```

`setInterval(function,time)` 是 window 对象的方法，它使某个函数每隔一段时间执行一次

通过 `clearInterval()` 可以停止定时器

```js
timer = setInterval(function(){},20);
clearInterval(timer);
```

###### 定时器运动注意点

```js
startBtn.onclick = function(){
    setInterval(function(){
        nowleft +=2;
        oDiv.style.left = nowleft + "px";
    },20);
}
```

如以上脚本当点击开始按钮时盒子以 2px/20ms 速度运动，连续点击按钮会导致盒子运动加快，解决方案，设表先关

```js
startBtn.onclick = function(){
    cleatInterval(timer);
    timer = setInterval(function(){
    	nowleft +=2;
    	oDiv.style.left = nowleft + "px";
    },20);
}
```

### JSON

###### JSON 语法

```js
var obj = {
    "name": "zhangsan",
    "age": 18，
    "sex": "male"
};
```

JSON 语法为 `"k":v` 形式，可以通过点语法或 `[]` 来获取属性的值

```js
obj.name
obj["name"]
```

###### JSON 的嵌套

json 里的 v，也可以还是一个 json

```js
var obj = {
    "name": "lisi",
    "age": 18,
    "sex": "male",
    "hobby": {
        "hobbyOne": "basketball",
        "hobbyTwo": "soccer",
        "hobbyThree","baseball"
    }
};
```

###### JSON 的添加与删除

通过点语法可以向 JSON 中添加值

```js
var obj = {
    "name": "zhangsan",
    "age": 18,
};
obj.sex = "male";
```

使用 delete 关键字可以删除 json 中某个属性

```js
delete obj.age;
```

###### JSON 的遍历

json 是通过 `for···in` 语句来遍历的

```js
for(var k in obj) {
    alert(obj[k]);
}
```

### 运动框架

让 oDiv 盒子 3000ms 后运动到终点

```js
animate(oDiv,{"width":700,"height":250},3000)
```

### 异步和回调函数

###### 同步和异步

同步 Synchronous：程序从上到下依次执行

异步 Asynchronous：程序不再从上到下执行

JS 中的异步，需要异步语句，setInterval、setTimeout、Aajx、Node.js......，存在异步语句，则程序异步执行

###### 回调函数

异步的语句做完之后要做的事情

```js
var count = 0;
var timer = setInterval(function(){
    console.log(count);
    count++;
    if(count>300){
        clearInterval(timer);
        callback();
    }
},20);
function callback(){
    alert("timer finished");
}
```

###### apply 和 call 语句

在回调函数中，不能直接使用 this 来表示当前对象，但通过 apply 或 call 语句可以实现

```js
var obj = {
    "name": "zhangsan",
    "age": 12
};
function callback(){
    console.log(this.name)
}
callback.call(obj);
callback.apply(obj);
```

apply 和 call 语句功能相同，都是让函数调用，并且给函数设置 this 表示谁，他们的区别是当函数有参数时，参数传入方式不同

```js
function callback(a,b,c){}
callback.call(obj,param1,param2,param3);
callback.apply(obj,[param1,param2,param3]);
```

###### 缓冲

缓冲算法

```js
function linear(t, b, c, d){
    return c * t / d + b;
}
function easeIn(t, b, c, d){
    return c * ( t /= d) * t + b;
}
function easeOut(t, b, c, d){
    return -c * (t /= d) * (t - 2) + b;
}
```

t 表示当前帧编号，b 表示其实位置，c 表示变化量，d 表示总帧数

函数的返回值，就是 t 这一帧，元素应该在的位置

### 延时器

通过 `setTimeout()` 可以设置延时器，延时器在指定时间后执一次

```js
setTimeout(function(){
    alert("延时器");
},3000);
```

延时器也可以清除

```js
clearTimeout();
```

### 函数节流

函数节流，即希望一些函数不要连续的触发

经典函数节流模型

```js
var lock = true;
input.onclick = function(){
    if(!lock) return;
    lock = false;
    setTimeout(function(){
        lock = true;
    },1000);
}
```

