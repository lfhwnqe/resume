# 调试javascript
 调试神器：console.log()  
- javascript一般的流程是一行一行运行 
- js引擎默认换行为一跳语句
- 先声明，再赋值
- 赋值的标示名称第一个字母可以是美元符号$ _
- javascript声明有保留字不能赋值
- 表示符不能有）"-" 中横线
# 变量命名规则  
- 第一个字符，可以是任意Unicode字母（包括英文字母和其他语言的字母），以及美元符号（$）和下划线（_）
- 第二个字符及后面的字符，除了Unicode字母、美元符号和下划线，还可以用数字0-9  
#### 下面这些都是合法的标识符:
```
arg0
_tmp
$elem
π
```
#### 下面这些则是不合法的标识符:
```
1a  // 第一个字符不能是数字
23  // 同上
***  // 标识符不能包含星号
a+b  // 标识符不能包含加号
-d  // 标识符不能包含减号或连词线
```
#### 中文是合法的标识符，可以用作变量名
```
var 临时变量 = 1;
```
> JavaScript有一些保留字，不能用作标识符：arguments、break、case、catch、class、const、continue、debugger、default、delete、do、else、enum、eval、export、extends、false、finally、for、function、if、implements、import、in、instanceof、interface、let、new、null、package、private、protected、public、return、static、super、switch、this、throw、true、try、typeof、var、void、while、with、yield。    

另外，还有三个词虽然不是保留字，但是因为具有特别含义，也不应该用作标识符：Infinity、NaN、undefined
# JavaScript区块
JavaScript使用大括号，将多个相关的语句组合在一起，称为“区块”（block）。

与大多数编程语言不一样，JavaScript的区块不构成单独的作用域（scope）。也就是说，区块中的变量与区块外的变量，属于同一个作用域。
```
{
  var a = 1;
}

a // 1
```
上面代码在区块内部，声明并赋值了变量a，然后在区块外部，变量a依然有效，这说明区块不构成单独的作用域，与不使用区块的情况没有任何区别。所以，单独使用的区块在JavaScript中意义不大，很少出现。区块往往用来构成其他更复杂的语法结构，比如for、if、while、function等。
# javascript数据类型
## 概述
JavaScript 语言的每一个值，都属于某一种数据类型。JavaScript 的数据类型，共有六种。（ES6 又新增了第七种 Symbol 类型的值）

- 数值（number）：整数和小数（比如1和3.14）
- 字符串（string）：字符组成的文本（比如"Hello World"）
- 布尔值（boolean）：true（真）和false（假）两个特定值
- undefined：表示“未定义”或不存在，即由于目前没有定义，所以此处暂时没有任何值
- null：表示无值，即此处的值就是“无”的状态。
- 对象（object）：各种值组成的集合
通常，我们将数值、字符串、布尔值称为原始类型（primitive type）的值，即它们是最基本的数据类型，不能再细分了。而将对象称为合成类型（complex type）的值，因为一个对象往往是多个原始类型的值的合成，可以看作是一个存放各种值的容器。至于undefined和null，一般将它们看成两个特殊值。

对象又可以分成三个子类型。

- 狭义的对象（object）
- 数组（array）
- 函数（function）
# typeof运算符
JavaScript有三种方法，可以确定一个值到底是什么类型。
- typeof运算符（判断函数是什么类型）
- instanceof运算符
- Object.prototype.toString方法
# 布尔值
布尔值代表“真”和“假”两个状态。“真”用关键字true表示，“假”用关键字false表示。布尔值只有这两个值。

下列运算符会返回布尔值：

- 两元逻辑运算符： && (And)，|| (Or)
- 前置逻辑运算符： ! (Not)
- 相等运算符：===, ! ==, ==,! =
- 比较运算符：>，>=，<，<=
# 运算符
JavaScript中运算符主要用于连接简单表达式，组成一个复杂的表达式。常见的有算数表达式、比较表达式、逻辑表达式、赋值表达式等，也有单目运算符，指操作原始表达式。大多数运算符都由标点符号组成（+、>=、!），也有关键字表示的运算符，如typeof、delete、instanceof等。

一些运算符可以作用于任何数据类型（typeof），但大部分操作符希望操作数是特定的类型，而且大部分操作符会计算出（我们也常说返回）一个特定类型的值（typeof返回的全是string）。在JavaScript中运算符通常会根据需要对操作数进行类型转换，乘法操作符希望操作数是数字，但是 "3" * "5"也是合法的，JavaScript会自动将其转换为数字计算，返回Number 15。

有些操作符对不同的数据类型有不同的含义，比如 +
- 在两个操作数都是数字的时候，会做加法运算
- 两个参数都是字符串或在有一个参数是字符串的情况下会把另外一个参数转换为字符串做字符串拼接
- 在参数有对象的情况下会调用其valueOf或toString
- 在只有一个字符串参数的时候会尝试将其转换为数字
- 在只有一个数字参数的时候返回其正数值
```
console.log(2+4);//6
console.log("2"+"4");//"24"
console.log(2+"4");//"24"
console.log(2+new Date());//"2Mon Jan 20 2014 17:15:01 GMT+0800 (China Standard Time)"
console.log(+"4");//4 
```
_注意:_ valueOf优先级高于toString  
_注意:_ +obj 如果obj内是字符串，会强制转化成数字再返回
# 运算符类型
## 算数运算符
- 加法运算符（Addition）：x + y
- 减法运算符（Subtraction）： x - y
- 乘法运算符（Multiplication）： x * y
- 除法运算符（Division）：x / y
- 余数运算符（Remainder）：x % y
- 自增运算符（Increment）：++ x 或者 x++
```
执行前置递增和递减操作时，变量的值都在语句被求值以前改变的（这种情况被称为副效应）
    例：
    var age = 29;       
    var anotherAge = --age + 2;
    alert(age);         //输出28
    alert(anotherAge);        //输出30
    由于前置递增和递减操作与执行语句的优先级相等，因此整个语句会从左至有被求值，例：
    var num1 = 2;
    var num2 = 20;
    var num3 = --num1 + num2;        //等于21
    var num4 = num1 + num2;        //等于21

    后置型
    后置递增递减语法不变，但区别是：即递增递减操作是在包含它们的语句被求值之后才执行的，例：
    var num1 = 2;
    var num2 = 20;
    var num3 = num1-- + num2;        //等于22
    var num4 = num1 + num2;        //等于21
```
- 自减运算符（Decrement）：--x 或者 x--
- 求负运算符（Negate）：-x
- 数值运算符（Convert to number）： +x
## 赋值运算符
赋值运算符用于给变量赋值，最常见的赋值运算符，当然就是等号，表达式x=y表示将y赋值给x。除此之外，JavaScript还提供其他11个赋值运算符。
```
x += y // 等同于 x = x + y
x -= y // 等同于 x = x - y
x *= y // 等同于 x = x * y
x /= y // 等同于 x = x / y
x %= y // 等同于 x = x % y
x >>= y // 等同于 x = x >> y
x <<= y // 等同于 x = x << y
x >>>= y // 等同于 x = x >>> y
x &= y // 等同于 x = x & y
x |= y // 等同于 x = x | y
x ^= y // 等同于 x = x ^ y
```
## 比较运算符
比较运算符比较两个值，然后返回一个布尔值，表示是否满足比较条件。JavaScript提供了8个比较运算符。

```
== 相等
=== 严格相等
!=不相等
!== 严格不相等
< 小于
<= 小于或等于
> 大于
>= 大于或等于

```
# 布尔运算符
- ! 取反运算符
- && 且运算符
- || 或运算符
- condition? true case : false case 三元条件运算符
# 位运算符
- 或运算（or）：符号为|，表示两个二进制位中有一个为1，则结果为1，否则为0。
- 与运算（and）：符号为&，表示两个二进制位都为1，则结果为1，否则为0。
- 否运算（not）：符号为～，表示将一个二进制位变成相反值。
- 异或运算（xor）：符号为ˆ，表示两个二进制位中有且仅有一个为1时，结果为1，否则为0。
- 左移运算（left shift）：符号为<<
- 右移运算（right shift）：符号为>>
- 带符号位的右移运算（zero filled right shift）：符号为>>>
# 其它
## 小括号
在JavaScript中，圆括号是一种运算符，它有两种用法：如果把表达式放在圆括号之中，作用是求值；如果跟在函数的后面，作用是调用函数。

把表达式放在圆括号之中，将返回表达式的值。

## void
void运算符的作用是执行一个表达式，然后返回undefined。
## 逗号运算符   
逗号运算符用于对两个表达式求值，并返回后一个表达式的值
### JavaScript 定义了几种数据类型? 哪些是原始类型?哪些是复杂类型?

JavaScript 的数据类型，共有六种。（ES6 又新增了第七种 Symbol 类型的值）
1. 数值（number）
2. 字符串（string）
3. 布尔值（boolean）  
true（真）和false（假）两个特定值
4. undefined
5. null
6. 对象（object）  

##### 原始类型值  
_我们将数值、字符串、布尔值称为原始类型（primitive type）的值_ 

##### 复杂类型值  
_将对象称为合成类型（complex type）的值，因为一个对象往往是多个原始类型的值的合成，可以看作是一个存放各种值的容器。至于undefined和null，一般将它们看成两个特殊值_

### 如何判断一个变量是否是数字、字符串、布尔、函数

JavaScript有三种方法，可以确定一个值到底是什么类型。

- typeof运算符
```
typeof 123 // "number"
typeof '123' // "string"
typeof false // "boolean"
//数值、字符串、布尔值分别返回number、string、boolean

function f() {}
typeof f
//函数返回function

typeof undefined
//undefined返回undefined

typeof window // "object"
typeof {} // "object"
typeof [] // "object"
typeof null // "object"
//其他情况都返回object
```
- instanceof运算符
- Object.prototype.toString方法
###  == 与===有什么区别  

它们的区别是相等运算符（ == ）比较两个值是否相等，严格相等运算符（ === ）比较它们是否为“同一个值”。如果两个值不是同一类型，严格相等运算符（ === ）直接返回false，而相等运算符（ == ）会将它们转化成同一个类型，再用严格相等运算符进行比较。  
_注意：相等运算符隐藏的类型转换，会带来一些违反直觉的结果。_

```
'' == '0'           // false
0 == ''             // true
0 == '0'            // true

2 == true           // false
2 == false          // false

false == 'false'    // false
false == '0'        // true

false == undefined  // false
false == null       // false
null == undefined   // true

' \t\r\n ' == 0     // true
```

上面这些表达式都很容易出错，因此不要使用相等运算符（ == ），最好只使用严格相等运算符（ === ）。
以下代码的输出结果是?为什么?

```
console.log(1+1);   //2     在两个操作数都是数字的时候，会做加法运算
console.log("2"+"4");   //"24"      两个参数都是字符串或在有一个参数是字符串的情况下会把另外一个参数转换为字符串做字符串拼接
console.log(2+"4");     //"24"      原因同上
console.log(+"4");  //4       在只有一个字符串参数的时候会尝试将其转换为数字  
```

### 以下代码的输出结果是?

```
var a = 1;  
a+++a;  //等于（a++）+a ;  a++ 返回1，自增a等于2，so 1+2 =3
typeof a+2; //'number2'  typeof 优先级比加法运算符高，其实是(typeof a) + 2。起到了字符串拼接作用
//无输出结果 
```
