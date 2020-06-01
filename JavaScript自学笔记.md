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

