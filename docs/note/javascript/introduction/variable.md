# 变量

::: tip TIP
在 js 中变量代表一个值的名称。相当于人名一样，变量名是指向计算机中的某个内存地址。也可以理解为内存地址的代号。
:::

在JavaScript中变量就是用一个变量名表示，变量名只能有大小写英文、数字、$和_的组合，且不能用数字开头。变量名也不能是 js 的关键字，如while、switch等。声明一个变量用var语句
``` js
var a = '';
var $a;
var _a;
var a_007 = '007';
```
以上都是合格的变量名。

在 js 中，使用等号 = 对变量进行赋值。可以把任意数据类型赋值给变量，同一个变量可以反复赋值，而且可以是不同类型的变量，但是要注意只能用var声明一次，例如：
``` js
var a = '';
a = 321;
```
注意：这两行代码赋值的类型是不一样的，但是这种操作 js 是支持的。因为 js 是动态类型语言。


一次性声明多个变量:
``` js
//多个变量用逗号隔开
var a=1,b=2,c=3......;
```
## 常量: 
一旦声明就无法重新赋值
``` js
const a=1;
a = 1; // 报错 TypeError: Assignment to constant variable.
```

## 预编译（变量声明提前）
用var 声明变量带来的缺陷：

js 在设计之初，为了方便初学者学习，并不强制要求用var声明变量。这个设计错误带来了严重的后果：如果一个变量没有通过var声明就被使用，那么该变量就自动被声明为全局变量：
``` js
a = 1; // 不会报错 会自动在前面  添加 window.a = 1;
```
变量声明提前
``` js
//js当中  正常来说  打印一个未声明的变量 会报错: a is not defined
console.log(a); //不会报错 返回undefined
var a = 1;      //var a;  会在打印之前执行 从而得出 var 声明的变量会在当前作用域顶部最先执行
```
变量重复声明
用 var 声明的变量，他的作用于是函数级作用域的，并且变量名还可以重复声明，这是一个很致命的隐患。
``` js
var a = 1;
var a = 2; // 不会报错 后面覆盖前面  此时a的值为2
```
## ES6 中的变量声明let
let的优点: 
1. 阻止声明提前
``` js
    console.log(a); //Error: a is not defined
    let a = 1;  
```
2. 添加块级作用域，让if else if else while for ...都变成了作用域
``` js
    if (true) {
      let b = 0;
    }
    console.log(b);// Error: b is not defined
    //let的原理: 
	let a=100;
	//相当于:
	(function(){
		var _a=100;
		...
    })()
```
               

