PHP_day1(变量，函数，输出)  
=======================
1.变量
--
在PHP中，变量是以`$`开头的后面跟着变量名，格式为
```
$ 变量名=变量参数
```
变量名可以以字母，下划线开头，但不能以下划线开头,比如
```
$number=1;
$number1=2;
$_number=3;
```
这些是合法的，但下面这些变量，是错误的
```
$1var=1;/*不可以用数字开头，这次错误的示范*/
```
其次，变量区分大小写`$number`和`$Number`是两个不同的变量 

PHP是弱类型语言，变量类型区别在于符号（咋个说呢....)演示一下，大概就是这样   
```
$var1=1         #整型
$var2="hello" #字符串
$var3='c'     #字符
$var4=2.22   #浮点(双精度浮点)
``` 

2.函数
--
php的函数与Javascript函数很像，都是以`function`开头，格式为
```
function 函数名(变量1，变量2){
    #函数主体
}
```
比如
```
function add($var1,$var2){
    return $var1+$var2;
    #这段代码是一个简单的加计算，获取变量$var1和var2的值，并相加并返回
}
```
调用函数直接函数名+`()`里面跟着要传入的值,比如要调用上面的函数可以这么写
```
echo add(1,2);
```
最后得的值为3。  
在PHP中，函数是不区分大小写的，上面的函数也可以这么写
```
ADD(1,2);
Add(1,2);
AdD(1,2);
....就不写了
```
如果你嫌弃这样写不直白，还可以这样写
```
echo add(1+2);#区别于add(1,2)
```
这样写会报错，可以在函数名前加上`@`屏蔽报错，如
```
echo @add(1+2);
```
输出
--
php输出有两个，哟个`echo`,一个`print`，两个区别为  
+ `echo` - 可以输出一个或多个字符串
+ `print` - 只允许输出一个字符串，返回值总为 1