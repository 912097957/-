



# 							JavaScript基础篇

## **js组成部分**

```
1.ECMA script标准						js的基本语法
2.DOM document Object model    		 文档对象模型
3.BOM browser Object model  		 浏览器对象模型
```

```
注意:
在一对script中的代码哪一行出错了,那他后面的代码都不会执行
如果在第一对标签出错,第二对标签不受影响
中不用在script标签内写 type="text/javascript" 或者 language="javas
可以出现多个script标签一般我们把script代码放在body的最后
如果是引入代码的标签,那么里面绝对不要写其他东西
```

****

## 变量

```
变量的数据都是在内存中存储的
变量是用来操作数据的(存储和读取)
js中储存数据使用的是变量的方式
组成:
变量名  +  值  ==>数据
var num= 10; 
```

```
变量声明:有变量名 没有值 
var number;
声明一个变量,类似于开一个房间
var a,b,c,d,f;
同时声明多个变量,类似于开多个房间,没赋值
```

```
变量初始化: 就是变量声明加赋值
存储一个数字10:
var number= 10;
```

## 变量的命名

```
变量名的注意问题
1.变量名要有意义
2.变量名要规范 一般以字母,$符号,下划线开头,不能数字开头,后面可以加上字母,数字,$符号
3.变量名一般都是小写
4.变量名如果是多个单词,采用驼峰式命名,开头单词是小写,后面的单词首字母大写
5.不能使用关键字
```

## 变量的初始化

```
声明变量并赋值var num = 10;

声明多个变量,然后依次进行赋值:
var num1, num2, num3;
num1 = 1;
num2 = 2;
num3 = 3;

声明多个变量并赋值
var num1 = 1, num2 = 2, num3 = 3;

用弹框的形式输出一个变量alert(num);
把内容输出在控制台中console.log(num);
把内容输出在文档内document.write(num);
```

### 小案例:变量的交换

```
交换变量的第一种思路:借助第三方变量进行交换
var num1 = 10;
var num2 = 20;
声明一个零时变量temp并把num1的值取出来又存进这个零时变量
var temp = num1; //把num1的值取出来放进temp
var num1 = num2; //把num2的值放进num1中
var num2 = temp; //把temp的值取出放进num2中
console.log(num1);
console.log(num2);
```

```
第二种交换方式:一般用于数字的交换
var num1 = 10;
var num2 = 20;
num1 = num1 + num2; //把num1和num2的值相加并赋到num1中
num2 = num1 - num2; //此时num1的值为30,减掉num2的20等于10并赋进num2
num1 = num1 - num2; //减掉num2的20并赋进num1
console.log(num1, num2);
```

## 变量的储存

```
javascript的原始数据类型有:Number, String, Boolean, Undefined, Null, Object 
String				字符串类型 "小黑"  
Number				数字类型  1, 2, 3 
Null  				空类型,值只有null 一个对象指向为空时,此时赋值为null 
Boolean  			布尔类型  值为 true 或 false 真和假  
Undefined  			未定义,值只有undefined 
Object 				对象

什么情况下是undefined :     
var num;   
变量声明没有赋值,打印结果是undefined
或者函数没有明确返回值,如果接收了也是undefined 
```

## 获取变量类型

```
用typeof来获取数据的类型
typeoftypeof(空格)变量名;
typeof(变量名);

console.log(typeof(num));	//number类型
console.log(typeof(str));	//string类型
console.log(typeof(nul));	//Object类型
console.log(typeof(und));	//undefined类型
console.log(typeof(flag));	//boolean类型
console.log(typeof(obj));	//Object类型
```

### 数字类型

```
二进制 逢二进一
var num = 00000001;
十进制 逢9进一
var num1 = 012;
十六进制 逢f进一  123456789abcdef
var num2 = 0x12a;

数字类型有范围:最大值和最小值
Number.MAX_VALUE;	//数字的最大值
Number.MIN_VALUE;	//数字的最小值

判断一个结果是不是一个数字使用  isNaN(变量名)  来验证
console.log(isNaN(变量))

不要用小数去验证小数
var x = 0.1;
var y = 0.2;
var num = x + y;
输出结果并不是0.3

不要用NaN去验证NaN,它不等于它自己

总结:
    数字类型是:number
    无论是整数还是小数都是数字类型
    不要用小数去验证小数这是一个bug
    不要使用NaN判断是不是NaN,应该使用isNaN(变量名或者值)
    想要表示十进制就是正常的数字
    想要表示八进制是0开头
    想要表示十六进制是0X开头
```

### 字符串类型

```
var str = "10"; //字符串类型
var str1 = '20'; //字符串类型
总结: 字符串可以使用单引号,也可以使用双引号
```

#### 查看字符串长度

```
var str = "ABCDEFGHLJKM"
console.log(str.length);	
字符串的长度是指元素的个数
一个字母数字都是一个元素
总结: 获取字符串的长度用 (变量名)str.length 获取 
```

#### 字符串拼接

```
var str1 = "10";
var str2 = "wa";
var str3 = str1 + str2;
console.log(str3);	//10wa
总结: 使用字符串+一个字符串会的到一个拼接的字符串
总结: 只要有一个是字符串,其他的数字,那么也是拼接而不是相加
```

```
var str1 = "2";    
var str2 = 2;    
console.log(str1*str2);	//4
总结: 字符串除了加法是拼接字符串,其他运算符都是转换为数字进行运算
总结: 如果一个字符串-一个数字,那么浏览器会自动把这个字符串转化为数字  叫做隐式转换
```

### 数字类型转换

```
字符串类型转整数 parseInt()			
```

```
字符串类型转小数  parseFloat()
```

```
字符串转为数字 Number()			//强制转换,但凡包含一个非数字,结果皆NaN(非数:不是一个数字)
```

### 其他类型转字符串类型

```
变量.toString()
```

```
var sum = 10;
var sum1;
var sum2=null;
console.log(sum.toString());//10
console.log(sum1.toString());//报错 没有值就是unde没有意义
console.log(sim2.toString());//报错 null是空,没有值也没有意义

总结: 如果变量有意义调用.toString()     主动  我要进行转换
总结: 如果变量没有意义调用String()      被动  我被强行转换
```

### 其他类型转布尔类型

```
Boolean()   
true  		为1 
false 	    为0
```

## 操作符(运算符)

```
算数运算符      + - * / %   加 减 乘 除 取余
由算数运算符连接起来的算数运算表达式
```

```
一元运算符  ++  --
这个操作符只需要一个操作数就可以进行运算的运算表达式  
++ 和  -- 都是运算符
++ 和  -- 都可以在前在后
++ 在后 先参与运算,再加1
++ 在前 自身先加1,然后再参与运算
```

```
二元运算符  + - * / %  (算数运算符)
需要两个操作数的运算表达式
或者需要三个操作数的运算表达式,可以是数字,变量,表达式
```

```
三元运算符  ?  :
三元表达式: 2 > 1 ? 2 : 1
判断2是否大于1,是则返回2,不是则返回1
```

```
复合运算符 +=  -=  *=  /=  %=  加等于 减等于 乘等于 除等于 
复合运算表达式:由复合运算符连接起来的表达式
```

```
关系运算符 
>大于  
<小于  
>=大于等于 
<=小于等于  
==等于等于(不严格)  
===绝对等于(严格)  
!==不等于(不严格)  
!===绝对不等于(严格)

关系运算表达式:由关系运算符连接起来的运算表达式
关系运算符返回值是布尔类型boolean 只有true 和 false 也就是真和假
```

```
逻辑运算符  &&  ||  !   与--并且    或--或者   非--取反 不是
逻辑运算表达式:由逻辑运算符连接起来的表达式

表达式1&&表达式2  两者都满足     返回true  否则返回false 
表达式1||表达式2  单方面满足     返回true  否则返回false 
表达式1!表达式2   取反           返回true  否则返回false 
```

## 字面量赋值

```
字面量: 直接给变量赋值的形式
var num = 10;

这个不是字面量赋值,而是通过其他变量进行赋值
var x = 10;
var y = x; 
```

## 流程控制

```
1. 顺序结构:    从上到下,从左到右 的执行顺序(不是很严谨)
2. 分支结构:    if语句, if-else语句, if-else if-else if...语句, switch-case语句, 三元表达式
3. 循环结构:    while循环, do-while循环, for循环, 后期还有个for-in循环
```

### 分支语句之if语句

```
if语句: 如果  主要是判断
语法: 
if(表达式){  
	代码块
}
```

### 分支语句之if-else语句

```
if-else语句: 如果  主要是判断
语法: 
if(表达式){  
	代码块1
}else{  
	代码块2
}
```

### 三元表达式

```
三元表达式运算符号:    ?    :
语法:            
var 变量 = 表达式1 ? 表达式2 :表达式3
执行过程:            
问表达式1的结果是true还是false,如果是true则执行表达式2,然后把结果赋给变量,如果是false,则执行表达式3,把结果赋给变量
```

### 分支语句之if-else if语句

```
语法:
if(表达式){
	代码块1
}else if(表达式2){
	代码块2
}else if(表达式3){
	代码块3
}else(表达式4){
	代码块4....}....
	
执行顺序:
	先执行表达式1,如果结果为true,执行代码块1,结果为false,则执行表达式2
	如果表达式2结果为true,执行代码块2,结果为false,则执行表达式3
	如果表达式3结果为true,执行代码块2,结果为false,则执行表达式4
	如果表达式4结果为true,执行代码块3,结果为false,则执行表达式5
	....以此类推
```

```
if语句: if语句只有一个分支
if-else语句: if语句只有两个分支,最终执行一个分支
if-else if-else if-else if....else语句: 多个分支,但最终也是只执行一个分支
```

### 分支语句之switch-case语句

```
switch-case语句是分支语句下的多分支语句
语法:
var = 变量;
switch(表达式或者变量名) {    
case (值1):代码1;break;    
case (值2):代码1;break;    
case (值3):代码1;break;    
case (值4):代码1;break;    
多个case....    
default:代码5;}

执行过程: 
    获取表达式的值,和值1比较,如果一样则执行代码1,遇到break就跳出语句,后面的代码不执行
    如果表达式的值和值1不一样,则和值2比较,如果相同则执行代码2,遇到break就跳出语句,后面的代码不执行
    如果表达式的值和值2不一样,则和值3比较,.....类推
```

```
值得注意的是:    
	1.Js是区分大小写的,存入变量的值如果是字符串类型字母也是区分大小写的    
	2.default是可以省略的,default后面的break也可以省略    
	3.如果不加break,那么他会一直进行查找并输出,一般是输出内容一样才可以省略    
	4.switch-case语句中和case后面的值比较的是严格模式
```

## 分支语句总结

```
分支语句: if 语句 只有一个分支,只执行一个 
用法:如果只需要满足一个条件 

if-else 有两个分支,最终只执行一个分支 
用法:如果满足不了这个条件就判断下一个条件

if-else if-else if-else... 有多个分支,最终也只执行一个分支 
用法:如果不满组第一个条件,就判定第二个条件,用来判断一个范围.直到满足后返回值 

switch-case 有多个分支,最终也只执行一个分支,必须要有break来结束语句并返回结果 
用法:用来对具体的值进行判断,并break返回结果

三元表达式
和if-else语句一样有两个分支,不是这个就是那个 
什么时候用if-else? 
什么时候用switch-case? 
如果是对一个范围进行判断,那么就使用if-else 
如果是对一个值进行判断,那么就使用switch-case进行判断
```

### 循环语句之while循环

```
循环是一件事重复做或者是重复做 循环要有循环的条件,循环的次数(计数器:记录循环的次数) 
语法: 
var i = 0; //计数器 
while (循环条件) {
循环体;    
计数器++; 
} 

执行过程: while先判断循环条件是true,还是false,如果是false,则不执行循环体,也就是大括号的内容; 如果是true,先执行循环体, 然后执行计数器,然后直接去---循环条件,再次判断是否成立,成立则继续执行循环体,否则跳出循环, 执行完循环体之后,计数器+1,再次去判断循环条件是否成立,成立则循环,不成立则跳出循环
```

### 循环语句之do-while循环

```
语法: 
do{  
	循环体; 
}while(条件); 

执行过程:先执行次循环体,再判断条件是否成立,不成立则跳出循环,如果成立,则继续执行循环体,然后再判断
```

### 循环语句之for循环

```
for循环语法:
for (var 表达式1; 表达式2; 表达式3){   
	循环体;
}

执行过程:   
先执行一次表达式1,然后判断表达式2,如果不成立则跳出循环;如果表达式2成立,执行循环体的代码,结束后跳到表达式3执行,然后再跳到表达式2,判断是是否成立,如果不成立,则跳出循环;如果表达式2成立,接着在执行循环体,再执行表达式3,再跳到表达式2..........
```

## 循环语句总结

```
while循环特点: 先判断一次,判定成立,执行循环体,判断不成立,则不执行循环体
do-while循环特点: 不管条件是否满足,它都会先执行一次循环体,再进行判断
for循环和while循环一样,先判定,成立再执行循环体,判断不成立,则不运行循环体
```

## break关键字

```
如果在循环中使用,则跳出当前循环
```

## continue关键字

```
遇到这个关键字会直接开始下一步循环
var i = 0;
while (i <= 10) {
	console.log("我好帅");
	continue; //直接开始下一次循环;
	i++;
}
```

## delete关键字

```
删除:
var num1 = 10;
num2 = 20;
delete num1; 					//把变量1删除
delete num2; 					//把变量2删除
console.log(typeof num1); 		// 结果为number  		结果没有被删除
console.log(typeof num2); 		// 结果为undefined 	隐士全局变量可以被删除
```



## 数组

```
数组:一组有顺序的数据
数组元素:数组中储存的每个数据,都可以叫数组元素,比如:储存了3个数据,就是数组中的3个元素
数组长度:数组中元素的个数,比如有3个元素就是这个数组的长度为3
数组索引(下标):用来存储或者访问数组中的数据的,下标从0开始计算,到长度减1

通过构造函数的方式创建一个数组 
var arr = new Array(一个数字);----这代表这个数组的长度
如果在Array(写下多个数字) 那个这个数组元素的个数就是数组的长度
数组的长度和数组的下标的关系:下标从0开始计算,到数组的长度减1停止

数组元素:数组中存储的每个数据,叫做数组元素,存储了5个数据,就是有5个元素
数组的长度:数组元素的个数叫数组的长度----数组.length ----- 数组的长度可以改变
数组索引:存储数据元素的编号,从0开始,到数组的长度-1结束
索引是用来存储和读取数组元素的
遍历数组:通过循环的方式找到数组的某个数据

如何获取数组中某个位置的值
console.log(数组名[下标]);
或者
var result=数组名[下标]; //创建一个变量来接收这个数据再打印
var result=arr[2];
console.log(result);

如何设置一个数组中的某个位置的值
数组名[下标]=值;
arr[2]=100;
```

### 数组的定义方式:

```
1:构造函数定义数组
var 数组名 = new Array(数据);
var 数组名 = new Array();        			    	  //定义了一个空数组,长度为0     
var 数组名 = new Array(一个数字);   			       //定义了一个数组.数组长度就是这个数字    
var 数组名 = new Array(值1,值2,值3...);     		    //定义了一个数组并且有多个数据

2:字面量定义数组
var 数组名 = [数据];
var 数组名 = [值1]; 								//定义了一个空数组
var 数组名 = [];   								 //定义了一个数组,数组长度为1,数据为值1

通过下标访问数组的元素值:	数组名 [下标];
通过下标设置数组的元素值:	数组名 [下标] = 值;
```

### 数组冒泡排序

```
var arr = [123, 354, 3521, 42132, 24, 34, 234];
for (var i = 0; i < arr.length; i++) {   
	for (var j = 0; j < arr.length; j++) {      
	if (arr[j] < arr[j + 1]) {         
		var temp = arr[j];         
		arr[j] = arr[j + 1];         
		arr[j + 1] = temp;         
		}   
	}
}
console.log(arr);      
```

## 函数

```1
函数:把重复的代码进行封装,在需要的时候进行调用
函数的作用:代码的重用

命名函数:有名字的函数称为命名函数
匿名函数:没有名字的函数称为匿名函数

函数命名:
get:获取值
set:设置值

函数的语法及定义:
function 函数名() {
	函数体
}

函数的调用:
函数名();

函数也是一种数据类型!!!
```

### 函数的定义方式

```
函数声明---函数定义
命名函数:
function 函数名(){ 
	函数体;
	}
name();
命名函数如果发生函数名重叠,后面的会覆盖前面的函数

匿名函数:
function (){   
函数体;
}

函数表达式:把一个匿名函数赋给一个变量就叫做函数表达式
var 变量名 = function(){
	函数体
};
注意:函数表达式后面必须加分号!因为它是一个赋值的过程
函数表达式如果发生函数名重叠,函数表达式不存在冲突问题
如果是函数表达式,那么此时前面的变量中存储的就是一个函数,而这个变量就相当于是一个函数,就可以直接加小括号调用
```

### 函数的参数

```
函数参数:
在定义函数的时候,函数名字后面的小括号里的变量就是参数,目的是在调用函数的时候,使用用户传进来的值进行操作;
此时函数定义的时候里面的小括号里的变量叫做参数;写了两个变量就有两个参数;

在函数调用的时候,按照提示的方式给变量赋值(把变量),,就叫传值或叫传参;
形参:函数在定义的是后小括号里的变量叫形参;
实参:函数在调用的是时候小括号里的变量叫实参,实参可以是数值,也可以是变量;
```

### 函数的返回值

```
在函数的内部有return这个关键字并且在关键字的后面有内容,这个内容被返回了
当函数调用之后,需要这个返回值,那么就定义这个变量接收即可

如果一个函数中没有明确的返回值,在调用的时候接受了,那么结果就是undefined

(没有明确返回值):
函数中没有return
return后面没有任何内容

return下面的代码是不会执行的

函数没有返回值,但是在调用的接收了,结果为undefined
变量声明了,没有赋值,结果也是undefined
如果函数中有return,那么这个函数就有返回值
如果函数中没有return,那么这个函数就没有返回值
如果一个函数有参数,就说明这是一个有参数的函数
形参的个数和实参的个数可以不一致

function f1(){
	 
}
这是一个无参数的函数

function f1(x,y){
}
这是一个有参数无返回值的函数

function f1(){
	 return 100;
}
这是一个无参数有返回值的函数

function f1(x,y){
	 return x+y;
}
这是有个有参数有返回值的参数(用的最多)
```

### 函数自调用

```
函数的自调用：没有名字;  
调用------声明的同时,直接调用,它是一次性的
一般来说我们调用一个函数需要先定义,后调用,如果没有函数名就无法调用,但是函数自调用出现了 
例如:

function () {     
console.log("小杨好帅啊");
}
这样我们是无法调用的

下面这样就可以:函数自调用(用一个括号括起来)
(function () {
	console.log("小杨好帅啊");
});
(); //小杨好帅啊
```

### 函数作为参数使用

```
函数可以作为参数使用,如果一个函数作为参数,那么我们可以说这个参数(函数)是回调函数
只要是看到一个函数作为参数使用了,那么就是回调函数
函数的参数里可以存储任何类型

function sayHi(fn) {
	console.log("我好帅");
	fn(); 					//fn此时是f函数,然后在函数内部调用
}
function f() {
	console.log("我也好帅");
}
sayHi(f);
```

### 函数作为返回值使用

```
函数可以作为参数使用,也可以作为返回值使用

function f1() { 					//这里f1调用时返回一个函数
	console.log("f1函数调用了");
	return function () { 			//当f1函数被调用,这里就会返回一个值
		console.log("这是一个函数");
	};
}
var ff = f1(); 						//这里定义一个变量来接收返回值,此时ff就是上面的这个函数里面返回										的函数,ff储存了这个函数,那他就是一个函数就可以调用它
ff();								//此时变量ff在栈中储存的是这个函数的地址指向,加个括号调用,返回										的结果是内部函数执行的结果
```



## arguments对象

```
arguments 			获取用户传入的参数的值
arguments.length  	获取函数在调用时用户传入参数的个数
arguments			被当做伪数组使用-----伪数组

arguments---------->可以获取函数调用的时候,传入的参数的长度
arguments---------->它是一个对象,是一个伪数组
arguments.length---------->实参的个数
arguments.[下标]---------->实参的值
```

```
定义一个函数,如果不确定用户是否传入了参数,或者说不知道用户传进几个参数,没办法计算,但是如果在函数中知道了参数的个数,也知道了每个参数的值,可以使用arguments对象操作数组
```

## 作用域

```
作用域:使用范围
全局变量:声明的变量是使用var声明的,那么这个变量就是全局变量,全局变量可以在页面的任何位置使用
全局变量,如果页面不关闭,那么久不会释放,会占空间,消耗内存
```

```
局部变量:在函数内部定义的变量就是局部变量,外面不能访问
除了函数以外,在其他任何地方定义的变量都是全局变量
```

```
全局作用域:全局变量的使用范围
局部作用域:局部变量的使用范围
```

```
块级作用域:别的语言里一对大括号就可以看成是一块,在这个区域里定义的变量只能在这个区域中使用
但是在js中,在这个块级作用域中用var定义的变量,外面也能使用,说明js中没有块级作用域
```

```
扩展:隐士全局变量
声明的变量没有var
number = 100;
全局变量是不能被删除的:用var定义的变量
但是隐士全局变量可以被删除(没意义):没用var定义的变量
```

## 作用域链

```
作用域链:
当我们在使用变量时,如果当前作用域没有变量,就向上级去找,找不到就往上上级找,递增,直到找到为止或者找到最顶端没有这个变量的声明就报错

作用域链的查找顺序是由里向外，js执行代码顺序是自上往下

var num = 50;
function f1() {
	// var num = 40;
	function f2() {
		// var num = 30;
		function f3() {
			// var num = 20;
			function f4() {
				// var num = 10;
				console.log(num);
			}
			f4(); //当调用f3的时候,内部执行f4调用
		}
		f3(); //当调用f2的时候,内部执行f3调用
	}
	f2(); //当调用f1的时候,内部执行f2调用
}
f1(); //从最外层开始调用
```

## 预解析

```
预解析:在代码执行之前的做的事情
在执行之前会把变量声明和函数声明提升到当前作用域最顶端并赋值undefined
预解析中,变量的提升,只会在当前的函数作用域中提升,提升到当前作用域的最上面
函数中的变量只会提升到函数作用域的中的最前面,不会出去
预解析中会分段,多对的script标签函数重名,预解析的时候不会冲突
函数的声明提升会比变量的声明提升优先级高

var num; //下面在打印的时候相当于在这里声明一个变量但是没有赋值,没有赋值的变量值默认为undefined
console.log(num);
var num = 10;

f1(); //这里同理:如果把函数调用放在上面,函数在调用时会把函数声明提升到作用域的顶端,并默认赋值 																						undefined
function f1() {
	//var num; //下面打印时相当于在这块作用域声明了一个变量num,并赋值undefined
	console.log(num);
	var num = 15;
}
f1(); //这里输出的是undefined,因为相当于在打印之前声明了一个num但没有赋值,然后默认赋值undefined

--------------------------------------------------------------------------------------

f1();
console.log(c); //这里可以访问到下面得隐式全局变量
console.log(b); //这里可以访问到下面得隐式全局变量
console.log(a); //这里访问不到函数里的局部变量,没声明没赋值会报错
function f1() {
	var a = b = c = 9; 
	拆解:
	var a;
	a = 9; //局部变量
	b = 9; //隐士全局变量
	c = 9; //隐士全局变量
	// 所以下面结果为9
	console.log(a); //结果为9
	console.log(b); //结果为9
	console.log(c); //结果为9
}
```

## 对象

```
对象:有属性和方法,具体指的某个事物
面向对象的特性:封装,继承,多态(抽象性);
对象的特点:特征和行为
特征:属性
行为:方法

对象:是一组无序属性的集合(数组有顺序(下标))
属性的值可以是任何类型
function Dog(name) {
	this.name(name);
};

js是一门什么样的语言:
是一门解释性语言			(解释一行执行一行)
是一门脚本语言				 (运行在浏览区客户端的一门语言)
是一门弱类型语言		 	(声明变量都用var)
是一门基于对象的语言
是一门动态类型的语言:
1.代码(变量)只有执行到这一行的时候,才知道这个变量中到底存储的是什么,如果是对象,就有对象的属性的值和方法,如果是变量就是这个变量的值 
2.对象没有什么,只要点了,通过点语法,那么就可以为对象添加属性和方法

点语法
对象.名字 = 值;
对象.方法名字 = 函数;

创建对象的方式:
1. 调用系统的构造函数创建对象  
var obj = new Object ();
2. 自定义构造函数的方式创建对象 
var obj = new 自定义构造函数名(首字母大写)();
3. 字面量的方式创建对象
var obj = {};
```

## 创建对象的三种方式

```
1.调用系统的构造函数创建对象     
var 变量名 = new Object();  //Object 是系统的构造函数
```

```
var obj = new Object();
// 对象有特征---属性和行为----方法
// 添加属性: 对象.名字=值;
obj.name = "小苏";
obj.age = 18;
obj.sex = "女";
//添加方法: 对象.名字=函数;
obj.eat = function () {  
	console.log("我喜欢吃油炸榴莲");
};
obj.play = function () {
	console.log("我喜欢玩飞机");
};

console.log(obj.name); //获取并输出属性;
console.log(obj.age); //获取并输出;
console.log(obj.sex); //获取并输出;

// 方法的调用
obj.eat(); //调用吃
obj.play(); //调用玩//
```

```

自定义构造函数创建对象,我要自己定义一个构造函数---->自定义构造函数,创建对象
函数和构造函数的区别:名字是不是大写(首字母大写)

2.自定义构造函数创建对象
function 构造函数名首字母大写(参数) {
	this.属性 = 值;
	this.属性 = 值;
	this.方法 = function () {
		方法体;
	}
}

var 变量名 = 构造函数名首字母大写(传入参数);		//创建对象(实例化对象并初始化)
变量名.方法();
```

```
3.字面量方式创建对象
var obj = {}; //此时是空对象
	obj.name = "小明";
	obj.age = 19;
	obj.sex = "男";
	obj.sayHi = function () {
	console.log("你好呀");
}
obj.sayHi();

//优化写法:舍去了前面的对象名,等号用冒号代替,末尾用逗号连接----->这是一个整体
var obj1 = {
	name: "小明",
	age: 18,
	food: "烤鸡",
	sayHi: function () {
		console.log("你好,我是" + this.name)
	},
	eat: function () {
		console.log("今天吃了" + this.food)
	}
};
obj1.sayHi();
obj1.eat();

字面量创建对象的缺陷:一次性的对象(这个对象一开始就写死了)这种方法不好改值,要改值只能到源码里去改
```

### 自定义构造函数创建对象做了几件事(new)

```
new的执行过程:
1.在内存中开辟空间(申请一块空闲的空间),储存创建的新的对象
2.把this设置为当前对象
3.设置对象的属性和方法的值
4.把this这个对象返回
```

## 总结JS语言特点

```
js是一门什么样的语言:
是一门解释性语言			(解释一行执行一行)
是一门脚本语言				 (运行在浏览区客户端的一门语言)
是一门弱类型语言		 	(声明变量都用var)
是一门基于对象的语言
是一门动态类型的语言:
1.代码(变量)只有执行到这一行的时候,才知道这个变量中到底存储的是什么,如果是对象,就有对象的属性的值和方法,如果是变量就是这个变量的值 
2.对象没有什么,只要点了,通过点语法,那么就可以为对象添加属性和方法

点语法
对象.名字 = 值;
对象.方法名字 = 函数;
```

## 获取该变量(对象)属于什么类型的

```
语法:
变量 instanceof 类型的名字 -------> 返回的结果是布尔类型,true就是这种类型,false就不是这种类
	
在当前对象的方法中是可以访问当前这个对象的属性的值的
在当前的对象方法中,可以使用this关键字代表当前的对象
```

## 工厂模式创建对象

```
过程:创建一个函数,在函数里创建一个对象,添加属性,添加方法,最后返回这个对象,定义一个变量接受这个对象,此时这个变量就是一个对象,然后就可以调用对象的方法
每当调用一次函数就创建一个对象,用函数传参的方式

function createObject(name, age) { //传参   
	var obj = new Object();   //这里创建两个变量接收传进来的参数   
	obj.name = name;   
	obj.age = age;   
	obj.sayHi = function () { //添加一个方法      
		console.log("大家好,我叫" + this.name + "," + "我今年:" + this.age + "了");   
};   
	return obj; //返回这个对象
};

	// 创建一个人的对象
	var per1 = createObject("小芳", 18); //定义参数传进去并接收
	per1.sayHi();
	
	// 创建另一个人的对象
	var per2 = createObject("小红", 20); //定义参数传进去并接收
	per2.sayHi();
	
	//这样就实现了工厂模式创建不同对象
```

## 获取对象属性的另外写法

```
function Person(name, age, sex) {  
	this.name = name;   
	this.age = age;   
	this.sex = sex;   
	this.play = function () {      
		console.log("喜欢玩游戏");   
	}
}
var per = new Person("小红", 18, "女"); //创建一个对象并传值并接收返回值
//	改值:
// per.name = "小明";
// 另一种写法
//per["name"] = "小单";

//	访问一个对象的属性不一定使用.语法
//	还可以console.log(per["name"]); //可以使用中括号的方式,里面是双引号写属性的名字

//	调用对象的方法可以这样写
per.play();
per["play"]();
```

## json格式的数据

```
json数据的格式:一般都是成对的,是键值对
json也是对象,数据都是成对的,一般json格式的数据无论是键还是值都是用双引号扩起来的
如果看到对象的属性和值都有双引号,那就是json格式的对象

var json = {
	"name": "小明",
	"age": "10",
	"sex": "男",
};
// 这个对象里面没有索引,所以不能用for循环遍历的
console.log(json.name); //这是可以的 
console.log(json["name"]); //这也是可以的
// 还可以 
var key = "name"; 			//定义一个变量来接收这个属性名
//var key = "height"; 		//定义一个变量来接收这个属性名  但是由于Js是一门动态类型的语言,没有什么								  就定义什么,所以赋值undefined
console.log(json[key]); 	//这也是可以的
```

## 遍历对象for-in

```
for循环不能遍历对象,但是for-in可以

for (var key in json) { 			//定义一个变量key接受对象里的属性名,属性名里存储着属性值  
	console.log(key + "属性的值为==>" + json[key]);
}

key是一个变量,这个变量中存储的是对象的属性名字
```

## 简单数据类型和复杂数据类型

```
原始数据类型: number string boolean undefined null object 
其中简单类型(值类型) number string boolean  
复杂类型(引用类型): Object 
空类型: undefined null
```

```
值类型的值在哪一块空间中储存?
栈中储存

引用类型的值在哪一块空间中存储?
在栈和堆中存储:一个存该对象的地址,一个存着对象数据
```

```
☆值类型之间传递,传递的是值 

function f1(x) {              		// 3.这个变量中存储的是传入的10	   
	x = 100;                 	    // 4.这时x的值又改为100          
} 
var num = 10;						// 1.先执行这段代码,在栈中申请一块空间存储10
f1(num);							// 2.然后调用这个函数时,将10赋值一份传入函数里的X变量,此时在栈										中开辟了一个x空间,赋值为10	
console.log(num) //10             	// 5.所有num的值和X的改变没有关系
```

```
☆引用类型的之间传递的是地址 
var obj = {               			 //1.此时obj这个(变量)存储在栈中,值为地址
	name : "小明"          	        //2.这个对象属性存储在堆中
}; 
function f1(x) {   
	x.name = "小红"; 			    	//5.这个函数参数里的x参数对象指向了0X120并更改了属性值
} 
console.log(obj.name);               //3.打印这个属性时,指向了0X120这个地址
f1(obj);               				 //4.此时将obj当中存储的地址0X120这个地址复制给了x
console.log(obj.name);    			 //6.此时打印结果为小红(堆中的值被更改了)
```

## 内置对象

```
js有三大对象
1. 内置对象-------------js系统自带的对象
2. 自定义对象-----------自定义构造函数创建的对象
3. 浏览器对象-----------BOM
```

### 内置对象

```
Math			数字对象
Date			时间对象
String			字符串对象
Array			数组对象
Object			对象

如何验证变量是不是一个对象
console.log(Array instanceof Object);    //验证Array是不是对象---系统内置对象
var obj = {};
console.log(obj instanceof Object);      //验证obj是不是对象---自定义对象		
```

### Math对象

```
实例对象:通过构造函数创建出来的,实例化对象
静态对象:不需要创建,直接就是一个对象,方法(静态方法)直接通过这个对象名字.调用
实例方法必须通过实例方法去调用
静态方法必须通过大写的对象调用

Math对象操作的是数字
```

#### Math常用属性及方法

```
Math.PI 					//圆周率
Math.abs(值) 			   //获取绝对值
Math.ceil 					//向上取整
Math.floor 					//向下取整
Math.max 					//找出一串数字中的最大值
Math.min 					//找出一串数字中的最小值
Math.pow 					//计算一个数值的平方
Math.sqrt 					//计算一个数值的平方根
Math.random 				//返回一个随机数(重要)
//返回的是一个0到1之间的伪随机数,乘以100是让这个数字变大,需要在多少之内,就乘以多少+1

//返回一个100以内的随机数字
console.log(parseInt(Math.random() * 100 + 1));
```

### Date对象

```
Date时间
创建实例对象 ----- 创建这个实例对象时如果不传值,返回的是当前服务器时间

var time = new Date();
//返回的时间是毫秒值 从1997年1月1日开始
var dd = Date.now();
console.log(dd);


var time = new Date();
//获取年份
console.log(time.getFullYear());
//获取月份----美国是从0月开始算,所以需要加1 
console.log(time.getMonth() + 1);
//获取一周的第几天
console.log(time.getDay());
//获取这个月的第几天(几号)
console.log(time.getDate());
//获取小时
console.log(time.getHours());
//获取分钟
console.log(time.getMinutes());
//获取秒数
console.log(time.getSeconds());
```

#### Date对象常用属性及方法

```
var time = new Date();
time.getFullYear(); 					//获取年
time.getMonth(); 						//获取月(从0开始)
time.getDate(); 						//获取日
time.getHours(); 						//获取小时
time.getMinutes(); 						//获取分钟
time.getSeconds(); 						//获取秒钟
time.getDay(); 							//获取星期(从0开始)
time.toDateString(); 					//英文格式
time.toLocaleDateString(); 				//数字格式
time.toTimeString(); 					//24小时格式时间
time.toLocaleTimeString(); 				//12小时格式时间
time.valueOf(); 						//毫秒

// 毫秒特殊写法用于兼容不支持的浏览器
var time = + new Date();
console.log(time);
```

### String对象

```
String 字符串对象

string ---------(小写)字符串类型 基本类型  可以看成是一个由字符组成的数组,但是js中没有字符
String ---------(大写)字符串类型 引用类型  可以看成是一个对象

结论:
字符是用一个单引号括起来的
但是在js中字符串可以使用单引号,也可以使用双引号
因为字符串可以看成数组,所以可以用for循环遍历
字符串的值看起来改变了,那时因为指向改变了,并不是指真的改变了

字符串特性:不可变性:字符串的值是不能改变的
```

#### String对象常用属性及方法

```
字符串的常用方法:
.length                                 //获取长度
.chaAt(索引)                         	  //返回字符串指定位置的字符,超出索引结果是空字符串(静态方法)
.fromChat(值,值,值)                      //返回一个ascii编码的字符串 
.concat(字符串1,字符串2,字符串3)            //返回一个拼接的字符串
.indexOf(要找的字符串,从第几个下标开始找)     //查找并返回一个指定的字符串的下标位置,没找到就返回-1
.lastIndexOf(要找的字符串)                 //从后往前查找并返回一个指定的字符串的下标位置,但是索引												还是从前往后的方式,没找到就返回-1
.replace(原来的字符串,要替换的字符串)         //用来替换字符串
.slice(开始的下标,停止的下标)                //截取字符串并返回截取的字符串
.split("要干掉的字符串","切割的个数")         //返回切割后的字符串
.substr(开始截取的下标,截取的个数(可以不写))   //返回一个指定开始位置和个数的截取的字符串
.substring(开始截取的下标,结束的下标)         //返回一个指定开始位置和结束位置的字符串(不包含结束位置)
.toLowerCase() 
.toLocaleLowerCase()                      //字符串转小写
.toUpperCase()   
.toLocaleUpperCase()                      //字符串转大写
.trim()                                   //切掉字符串两端的空格
```

### Array对象

```
创建数组的方式
1.构造函数
var arr1 = new Array();
2.字面量 
var arr2 = [];
```

#### Array对象常用的属性及方法

```
Array.isArray(变量或者对象)  也可以使用instanceof关键字        //判断这个对象是不是数组类型
.concat(数组1,数组2,数组3)								  //拼接数组
 
.every(函数 function(参数1,参数2,参数3))					 //判断数组中的元素是否满足某种条件,它要传入一个函数,返回值是布尔类型,函数作为参数使用,函数中有三个参数,第一个参数是元素的值,第二个是参数的索引,第三个参数是原来的数组(一般情况下不用),如果这个数组中每个元素的的值都符合条件,这返回true
.filter(函数  function(参数1,参数2,参数3))					 //筛选判断这个数组中符合条件的元素并															返回成新的一个数组
.forEach(函数  function(参数1,参数2,参数3))					 //代替for循环遍历数组
.indexOf(元素的值)											//查找数组中指定元素的下标位置,没找																到返回-1
.join("插入的间隔符")										   //向数组内容插入一个间隔符----返回																值是字符串类型
.map(函数或者方法)										   //数组中每一个元素都要执行这个函数,														把执行后的结果重新全部放在一个新的数组中
.reverse()												   //反转数组
.slice(开始的下标,结束的下标)						 			//截取数组中的某一段元素,返回截取的															数值放在一个新的数组中,不包括终止下标
.splice(插入的位置(下标),删除的个数(一般为0),插入的元素之)		 //往数组任意位置插入,删除,替换一个新															的元素并返回这个数组

.sort(function (a, b) {									   //排序数组用的:固定写法
	if (a > b) {
		return 1;
	} else if (a == b) {
		return 0;
	} else {	
		return -1;
	};						
});			

四个必须要记住的方法
原数组.unshift()						//追加一个新的元素进元素组第一位---返回值是插入后的长度	  
原数组.push()							//追加一个新的元素进原数组最后一位---返回值是插入后的长度	
原数组.shift()							//删除数组第一位元素并返回这个删除的元素
原数组.pop()							//删除数组中最后一个元素并返回删除的值
```

## 基本包装类型

```
普通变量不能直接调用属性或者方法
对象可以直接调用属性和方法

基本包装类型本身是基本类型,但是在执行代码的过程中,如果这种类型的变量调用了属性或者方法,那么这种类型就不再是基本类型了,而是基本包装类型,那么这个变量也不是普通变量了,而是基本包装类型对象
```

```
var num = 10; 							 //普通变量;
num.split(); 						 	 //普通变量调用方法  结果为报错
var str = "hello";
var result = str.replace("ll", "HH"); 	 //此时内部str变量变成了对象

var num1 = 10; 							 //此时是基本类型  Number
console.log(num1.toString()); 			 //当他调用这个方法之后就变成了基本包装类型

如果是一个对象&&true,那么结果是true;
var flag = new Boolean(false);
var result = flag && true;

如果是一个true&&对象,那么结果是对象
var flag = new Boolean(false);
var result = true && flag;

var num2 = 10;
var num3 = String(num2);				 //这里是转换,没有new 是类型转换
var num3 = new Number(num2); 			 //这里new了,基本包装类型
```

# JavaScript中级DOM篇

## DOM的概念

```
BOM(Browser Object Model) 是指浏览器对象模型，浏览器对象模型提供了独立于内容的、可以与浏览器窗口进行互动的对象结构。

BOM由多个对象组成，其中代表浏览器窗口的Window对象是BOM的顶层对象，其他对象都是该对象的子对象。

js分为三个部分:
ECMAScript标准				    js的基本语法
DOM:	Documents Object Model   文档对象模型 ----操作页面元素
BOM:	Browser Object Model 	 浏览器对象模型 ----操作的是浏览器

文档:把整个html文件看成是一个文档,由于万物皆对象,所以把这个文档看成一个对象XMl文件也是一个文档

HTML:展示信息
XML:侧重存储数据

html文件可以看成是一个文档,那么这个文档就可以看成一个对象,文档中的所有的标签都可以看成是一个对象
页面中所有的标签都是一个元素(element),每个元素都可以看成是一个对象
标签可以嵌套,标签中有标签,元素中有元素

html页面中都有一个根标签---html---也叫根元素 
页面中的有一个根元素(标签--html),里面有很多的元素(有很多的标签,有很多的对象)

文档:一个页面就是一个文档
元素(element):页面中所有的标签都是元素,元素都可以看成是对象
节点(node):页面中所有的内容都是节点:标签,属性,文本
root:根

页面就是文档--document,文档中有根元素:html
由文档及文档中所有的元素(标签)组成的一个树形结构图,叫树状图(DOM树)

DOM对象----通过dom方式获取元素得到的对象
页面中的顶级对象: document
```

### DOM获取元素

```
获取元素的方式
根据id获取
document.getElementById("id名")
根据标签名获取
document.getElementsByTagName("标签的名字")
根据name属性的值获取元素(表单标签)
document.getElementsByName("name属性的值")
根据类样式的名字获取
document.getElementsByClassName("类样式的名字")
根据选择器获取一个
document.querySelector("#id的名字") 
根据选择器获取多个
document.querySelectorAll(".类样式的名字") 

//获取body
console.log(document.body)//获取的是元素
//获取title标签的值
console.log(document.title)//标签中的值
//给title标签添加值
document.title = "前端学习";
//获取html
console.log(document.documentElement);
```

### 操作基本标签的属性

```
操作基本标签的属性scr,title,alt,href,id 
操作表单标签的属性name,value,type,checked,selected,disabled,readonly

元素样式操作
对象.style.属性=值
对象.className=值
```

### 设置标签内容

```
设置标签中的文本内容,应该使用textContent属性,谷歌,火狐,支持,IE8不支持
设置标签中的文本内容,应该使用innerText属性,谷歌,火狐,支持,IE8都支持 是IE8的标准属性

获取标签中的文本内容
console.log(my$("dv").innerText);
console.log(my$("dv").textContent);

innerText和innerHTML的区别:
都可以设置标签的文本内容
如果要是值标签和内容推荐使用innerHTMl的方式
如果要获取标签中文本使用innerText, 也可以使用innerHTML
如果想要获取的是有标签的文本使用innerHTMl
```

### 设置元素的样式

```
设置元素的样式
对象.style.属性 = 值;
对象.className = 值;
对象.style.属性 = "值";
```

### 自定义属性

```
自定义标签: 标签原本没有这个属性, 为了存储数据, 自己添加的属性

自定义属性无法通过DOM的方式设置或者获取只能使用:   
获取
对象.getAttribute("自定义属性名字"); 			 //获取自定义属性的值
设置
对象.setAttribute("自定义属性的名字", "值"); 		//设置自定义属性
移除
对象.removeAttribute("属性的名字");			   //删除自定义属性
```

### 事件

```
HTML事件是发生在 HTML 元素上的事情
事件:一件事有事件源,触发和响应
事件三要素:事件源,触发,响应
```

### this关键字

```
如果是在当前的元素的事件中使用,那么this就是当前的对象
```

## 节点

```
节点的属性:作用:为了将来获取很多的节点,得到节点中的标签(元素),识别节点中的标签的元素
节点的类型:1标签节点,2属性节点,3文本节点

nodeType---1---标签节点,2---属性节点,3---文本节点
nodeName---标签节点--大写的标签名字,如果是属性节点---小写的属性名字,文本节点---#text
nodeValue---标签---null,属性---属性的值,文本---文本内容

判断一个节点是不是标签:if (node.nodeType == 1 && node.nodeName =="P")

凡是获取节点的代码在谷歌和火狐得到的都是相关节点
凡是获取元素的代码在谷歌和火狐得到的都是相关元素

从子节点和兄弟节点开始
凡是获取节点的代码在IE8中得到的是元素
凡是获取元素的相关代码,在IE8中得到的是undefined----元素的代码,IE8中不支持
```

### 获取节点及元素

```
console.log(my$("uu").parentNode)			   // 1.获取当前节点的父级节点console.log(my$("uu").parentElement);		  // 2.获取当前节点的的父级元素console.log(my$("uu").childNodes);		 	  // 3.获取当前节点的子级节点console.log(my$("uu").children);		 	     // 4.获取当前节点的子级元素console.log(my$("uu").firstChild);		 	    // 5.获取当前节点的第一个子级节点console.log(my$("uu").firstElementChild);	  // 6.获取当前节点的第一个子级元素console.log(my$("uu").lastChild);		        // 7.获取当前节点的最后一个子级节点console.log(my$("uu").lastElementChild);       // 8.获取当前节点的最后一个子级元素console.log(my$("uu").previousSibling);        // 9.获取当前节点的前一个兄弟节点
console.log(my$("uu").previousElementSibling); // 10.获取当前节点的前一个兄弟元素
console.log(my$("uu").nextSibling);   		   // 11.获取当前节点的后一个兄弟元节点
console.log(my$("uu").nextElementSibling);     // 12.获取当前节点的后一个兄弟元元素
```

## 元素的创建

```
1.document.write("标签代码及内容");  			  //如果在页面加载完毕后创建,那么页面中的内容会被覆盖
2.父级对象.innerHTMl="标签代码及内容";
3.document.createElement("标签名字"); 			//得到的是一个元素对象  
父级元素.appendChild(子级元素对象); 				//将加入新创建的元素加入 
父级元素.inerstBefore(新的子级对象,参照的子级对象);  

移除子元素  
父级元素.removeChild(要干掉的子级元素对象)

总结:
1.createElement---创建元素
2.appendChild---追加元素
3.insertBefore---插入元素
4.removeChild---删除子元素
```

## 事件绑定

```
三种方式:
1.对象.on事件名字=事件处理函数         缺陷:如果是多个相同事件注册用这种方式,最后一个执行,之前的被覆盖了

2.对象.addEventListener("没有on的事件名字",事件处理函数名,false);

3.对象.attachEvent("有on的事件名字",事件处理函数名)   				//用于兼容IE

总结绑定事件的区别:
addEventListener();
attachEvent();
相同点: 都可以为事件绑定函数

区别:
1.方法名不一样
2.参数个数不一样
3.addEventListener  			谷歌,火狐,IE11支持,IE8不支持
  attachEvent       			谷歌,火狐,IE11不支持,IE8支持
4.this不同
addEventListener 			   	中this是当前绑定事件的对象
attachEvent      				中this是window
5.事件名不同
addEventListener				事件的类型(事件的名字)没有on
attachEvent						事件的类型(事件的名字)有on
```

## 解绑事件

```
注意:用什么方式绑定事件,就应该用对应的方式解绑事件
1.解绑事件
对象.on事件名字=事件处理函数 ----> 绑定事件
对象.on事件名字=null ----> 解绑事件
2.解绑事件
对象.addEventListener("没有on的事件名",命名函数,false) -----> 绑定事件
对象.removeEventListener("没有on的事件名",命名函数,false) ----->解绑事件
3.解绑事件
对象.attachEvent("on类型事件",事件处理函数)----->绑定事件
对象.detachEvent("on类型事件",事件处理函数)----->解绑事件
```

## 事件冒泡

```
事件冒泡:多个元素嵌套,有层次关系,这些元素都注册了相同事件,如果里面的元素的事件触发了,外面的的该事件自动触发

如何阻止事件冒泡:
window.event.cancelBubble = true; 				IE特有,谷歌支持,火狐不支持
stopPropagation(); 								谷歌,火狐支持,IE不支持
```

## 事件监听

```
为按钮添加点击事件 
addEventListener()
参数1:事件的类型---事件的名字但是没有on
参数2:事件处理函数---函数(命名函数,匿名函数)
参数3:布尔类型,目前就写false
```

## 事件总结/监听/冒泡 /阻止

```
事件有三个阶段
1.事件捕获阶段:从外向内
2.事件目标阶段:最开始选择
3.事件冒泡阶段:从里向外

事件监听
addEventListener("没有on的事件类型",事件处理函数,控制事件冒泡或者捕获true/false)

window.event.cancelBubble = true;		阻止事件冒泡 ----> 谷歌IE8支持,火狐不支持
										window.event就是一个对象,是IE中的标准
										
e.stopPropagation();					阻止事件冒泡 ----> 谷歌火狐支持

window.event和e都是事件参数对象,一个是IE标准,一个是火狐标准
事件参数e在IE8中是不存在的,此时用window.event来代替

addEventListener中的第三个参数是控制事件阶段的

事件的阶段有三个:
通过e.eventPhase这个属性可以知道当前的事件是什么阶段的
如果这个属性的值是:
1--捕获阶段
2--目标阶段
3--冒泡阶段

一般都用冒泡阶段,很少用捕获阶段
冒泡阶段是从里向外的
捕获阶段是从外向内的

事件对象的属性和方法

- event.type 获取事件类型
- clientX/clientY     					所有浏览器都支持，窗口位置
- pageX/pageY       					IE8以前不支持，页面位置
- event.target || event.srcElement 		用于获取触发事件的元素
- event.preventDefault() 				取消默认行为
```

## BOM的概念

```
浏览器中有个顶级对象 window
页面中有个顶级对象 document
页面中的所有的内容都是属于浏览器的,页面中的所有内容都是属于window的
因为页面中的所有内容,都是window的,所以就不用写的

jquery中顶级对象:$  ==>jquery
```

### 系统对话框

```
window.alert()      文字弹窗
window.prompt()		带输入框弹窗
```

### 页面加载事件

```
window可以省略,onload这个事件很重要
onload事件----页面加载完成后

页面加载完成后再执行
window.onload = function () {
    document.getElementById("btn").onclick = function () {
        alert("你好呀");
    }
}

// 拓展事件-----页面关闭后才触发的弹窗事件
window.onunload = function () {
    alert("哈哈");
}
// 拓展事件-----页面关闭之前触发的弹窗事件
window.onbeforeunload = function () {
    alert("嘿嘿");
}
```

### window包含对象

#### location对象

```
Location 对象包含有关当前 URL 的信息
Location 对象是 Window 对象的一个部分，可通过 window.location 属性来访问
```

```
console.log(window.location);
结果:
console.log(window.location.hash);				//地址栏上#及后面的内容
console.log(window.location.host);				//主机名及端口号
console.log(window.location.hostname);			//主机名
console.log(window.location.pathname);			//文件的路径---相对路径
console.log(window.location.port);				//端口号
console.log(window.location.protocol);			//协议
console.log(window.location.search);			//搜索的内容
```

#### location对象方法

```
onload = function () {    
document.getElementById("btn").onclick = function () {        
	//设置跳转的页面的地址        
	location.href = "http://www.baidu.com"; 	 //属性----->必须记住     			
	location.assign("http://www.baidu.com"); 	 //方法 两者相同      
	location.reload(); 							 //重新加载,刷新        
	location.replace("http://www.baidu.com");    //这种方式没有历史记录,所以不能后退   
	}
}
```

#### History 对象

```
History 对象包含用户（在浏览器窗口中）访问过的 URL。
History 对象是 window 对象的一部分，可通过 window.history 属性对其进行访问
```

#### History 对象属性方法

```
window.history.length				//返回浏览器历史列表中的URL数量

window.history.go(); 				//加载history列表中的某个具体页面
window.history.back(); 				//加载history列表中的前一个URL
window.history.forward(); 			//加载history列表中的下一个URL
```

####  Navigator对象

```
//通过userAgent属性获取当前浏览器的类型
console.log(window.navigator.userAgent);
//通过platform属性判断浏览器所在的系统平台类型
console.log(window.navigator.platform);
```

#### Screen 对象

```
window.availHeight					//返回屏幕的高度（不包括Windows任务栏）
window.availWidth					//返回屏幕的宽度（不包括Windows任务栏）
window.height						//返回屏幕的总高度
window.width						//返回屏幕的总宽度
```



### 定时器

```
BOM中有两个定时器定时器:
setInterval(参数1,参数2)
参数1:函数
参数2:时间--毫秒----1000毫秒=1秒
返回值:该定时器的id
window.clearInterval(定时器的id);			//清除定时器

setTimeout(函数,时间);
参数1:函数
参数2:定时器的时间
返回值:该定时器的id
window.clearTimeout(定时的id);				//清除一次性定时器

执行过程:页面加载完毕后,过了一秒,执行一次函数的代码,又过了一秒,再执行函数
返回值就是定时器的id值
```

### 三大系列offset/scroll/client

```
offset系列:
元素的样式是无法通过对象.style.属性来获取(样式在内联样式中可以获取到)
offsetLeft:元素距离左边的距离
offsetTop:元素距离顶部的距离
offsetWidth:元素的宽度 (包括边框)
offsetHeight:元素的高度 (包括边框)
```

```
scroll系列:卷曲
scrollWidth:元素中内容的实际的宽度(没有边框),如果没有内容就是元素的宽度
scrollHeight:元素中内容的实际的高度(没有边框),如果没有内容就是元素的高度
scrollLeft: 向左卷曲出去的距离
scrollTop: 向上卷曲出去的距离
```

```
client系列:元素可视区域的大小
clientWidth:元素可是区域的宽,不包括边框
clientHeight:元素可是区域的高,不包括边框
clientLeft:左边框的宽度
clientTop:上边框的宽度
clientX:可视区域的横坐标
clientY:可视区域的纵坐标
```

```
pageXOffset 和 pageYOffset 属性返回文档在窗口左上角水平和垂直方向滚动的像素

pageXOffset 设置或返回当前页面相对于窗口显示区左上角的 X 位置
pageYOffset 设置或返回当前页面相对于窗口显示区左上角的 Y 位置

pageXOffset 和 pageYOffset 属性相等于 scrollX 和 scrollY 属性
```



### 获取元素计算后的样式属性的值

```
window.getComputedStyle(element, null)[style]		//谷歌,火狐支持
window.currentStyle[style]							//IE8支持
window.currentStyle.left
类似element.style
```



```
function getStyle(element, attr) {   
	return window.getComputedStyle ? window.getComputedStyle(element, null)[attr] : element.currentStyle[attr] || 0;
}
```

# 事件查询大全

| 鼠标事件               | 描述                                                         |
| ---------------------- | ------------------------------------------------------------ |
| **onClick**            | 鼠标点击事件                                                 |
| **onDblClick**         | 鼠标双击事件                                                 |
| **onMouseDown**        | 鼠标上的按钮被按下                                           |
| **onMouseUp**          | 鼠标按下后，松开时激发的事件                                 |
| **onMouseOver**        | 鼠标移动到某对象范围的上方时触发的事件                       |
| **onMouseMove**        | 鼠标移动时触发的事件                                         |
| **onMouseOut**         | 鼠标离开某对象范围时触发的事件                               |
| **onKeyPress**         | 键盘上的某个键被按下并且释放时触发的事件                     |
| **onKeyDown**          | 键盘上某个按键被按下时触发的事件                             |
| **onKeyUp**            | 键盘上某个按键被按放开时触发的事件                           |
|                        |                                                              |
| **页面相关事件**       | **描述**                                                     |
| **onAbort**            | 图片在下载时被用户中断                                       |
| **onBeforeUnload**     | 当前页面的内容将要被改变时触发的事件                         |
| **onError**            | 捕抓当前页面因为某种原因而出现的错误，如脚本错误与外部数据引用的错误 |
| **onLoad**             | 页面内空完成传送到浏览器时触发的事件，包括外部文件引入完成   |
| **onMove**             | 浏览器的窗口被移动时触发的事件                               |
| **onResize**           | 当浏览器的窗口大小被改变时触发的事件                         |
| **onScroll**           | 浏览器的滚动条位置发生变化时触发的事件                       |
| **onStop**             | 浏览器的停止按钮被按下时触发的事件或者正在下载的文件被中断   |
| **onUnload**           | 当前页面将被改变时触发的事件                                 |
|                        |                                                              |
| **表单相关事件**       | **描述**                                                     |
| **onBlur**             | 当前元素失去焦点时触发的事件                                 |
| **onChange**           | 当前元素失去焦点并且元素的内容发生改变而触发的事件           |
| **onFocus**            | 当某个元素获得焦点时触发的事件                               |
| **onReset**            | 当表单中RESET的属性被激发时触发的事件                        |
| **onSubmit**           | 一个表单被递交时触发的事件                                   |
|                        |                                                              |
| **滚动字幕事件**       | **描述**                                                     |
| **onBounce**           | 在Marquee内的内容移动至Marquee显示范围之外时触发的事件       |
| **onFinish**           | 当Marquee元素完成需要显示的内容后触发的事件                  |
| **onStart**            | 当Marquee元素开始显示内容时触发的事件                        |
|                        |                                                              |
| **编辑事件**           | **描述**                                                     |
| **onBeforeCopy**       | 当页面当前的被选择内容将要复制到浏览者系统的剪贴板前触发的事件 |
| **onBeforeCut**        | 当页面中的一部分或者全部的内容将被移离当前页面[剪贴]并移动到浏览者的系统剪贴板时触发的事件 |
| **onBeforeEditFocus**  | 当前元素将要进入编辑状态                                     |
| **onBeforePaste**      | 内容将要从浏览者的系统剪贴板传送[粘贴]到页面中时触发的事件   |
| **onBeforeUpdate**     | 当浏览者粘贴系统剪贴板中的内容时通知目标对象                 |
| **onContextMenu**      | 当浏览者按下鼠标右键出现菜单时或者通过键盘的按键触发页面菜单时触发的事件 [试试在页面中的<body>中加入onContentMenu="return false"就可禁止使用鼠标右键了] |
| **onCopy**             | 当页面当前的被选择内容被复制后触发的事件                     |
| **onCut**              | 当页面当前的被选择内容被剪切时触发的事件                     |
| **onDrag**             | 当某个对象被拖动时触发的事件 [活动事件]                      |
| **onDragDrop**         | 一个外部对象被鼠标拖进当前窗口或者帧                         |
| **onDragEnd**          | 当鼠标拖动结束时触发的事件，即鼠标的按钮被释放了             |
| **onDragEnter**        | 当对象被鼠标拖动的对象进入其容器范围内时触发的事件           |
| **onDragLeave**        | 当对象被鼠标拖动的对象离开其容器范围内时触发的事件           |
| **onDragOver**         | 当某被拖动的对象在另一对象容器范围内拖动时触发的事件 [活动事件] |
| **onDragStart**        | 当某对象将被拖动时触发的事件                                 |
| **onDrop**             | 在一个拖动过程中，释放鼠标键时触发的事件                     |
| **onLoseCapture**      | 当元素失去鼠标移动所形成的选择焦点时触发的事件               |
| **onPaste**            | 当内容被粘贴时触发的事件                                     |
| **onSelect**           | 当文本内容被选择时的事件                                     |
| **onSelectStart**      | 当文本内容选择将开始发生时触发的事件                         |
|                        |                                                              |
| **数据绑定**           | **描述**                                                     |
| **onAfterUpdate**      | 当数据完成由数据源到对象的传送时触发的事件                   |
| **onCellChange**       | 当数据来源发生变化时                                         |
| **onDataAvailable**    | 当数据接收完成时触发事件                                     |
| **onDatasetChanged**   | 数据在数据源发生变化时触发的事件                             |
| **onDatasetComplete**  | 当来子数据源的全部有效数据读取完毕时触发的事件               |
| **onErrorUpdate**      | 当使用onBeforeUpdate事件触发取消了数据传送时，代替onAfterUpdate事件 |
| **onRowEnter**         | 当前数据源的数据发生变化并且有新的有效数据时触发的事件       |
| **onRowExit**          | 当前数据源的数据将要发生变化时触发的事件                     |
| **onRowsDelete**       | 当前数据记录将被删除时触发的事件                             |
| **onRowsInserted**     | 当前数据源将要插入新数据记录时触发的事件                     |
|                        |                                                              |
| **外部事件**           | **描述**                                                     |
| **onAfterPrint**       | 当文档被打印后触发的事件                                     |
| **onBeforePrint**      | 当文档即将打印时触发的事件                                   |
| **onFilterChange**     | 当某个对象的滤镜效果发生变化时触发的事件                     |
| **onHelp**             | 当浏览者按下F1或者浏览器的帮助选择时触发的事件               |
| **onPropertyChange**   | 当对象的属性之一发生变化时触发的事件                         |
| **onReadyStateChange** | 当对象的初始化属性值发生变化时触发                           |

