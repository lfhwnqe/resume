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