# NaN是什么? 有什么特别之处?
NaN是 JavaScript 的特殊值，表示“非数字”（Not a Number），主要出现在将字符串解析成数字出错的场合。
```
5 - 'x' // NaN
```
上面代码运行时，会自动将字符串x转为数值，但是由于x不是数值，所以最后得到结果为NaN，表示它是“非数字”（NaN）。  
另外，一些数学函数的运算结果会出现NaN。
```
Math.acos(2) // NaN
Math.log(-1) // NaN
Math.sqrt(-1) // NaN

```
0除以0也会得到NaN。
```
0 / 0 // NaN
```
需要注意的是，NaN不是一种独立的数据类型，而是一种特殊数值，它的数据类型依然属于Number，使用typeof运算符可以看得很清楚。
```
typeof NaN // 'number'
```
NaN不等于任何值，包括它本身。
```
NaN === NaN // false
```
NaN在布尔运算时被当作false
```
Boolean(NaN) // false
```
NaN与任何数（包括它自己）的运算，得到的都是NaN。
```
NaN + 32 // NaN
NaN - 32 // NaN
NaN * 32 // NaN
NaN / 32 // NaN
```
# break与continue有什么区别?
break语句和continue语句都具有跳转作用，可以让代码不按既有的顺序执行。

break语句用于跳出代码块或循环。
```
var i = 0;

while(i < 100) {
  console.log('i当前为：' + i);
  i++;
  if (i === 10) break;
}
```
上面代码只会执行10次循环，一旦i等于10，就会跳出循环。  

continue语句用于立即终止本轮循环，返回循环结构的头部，开始下一轮循环。
```
var i = 0;

while (i < 100){
  i++;
  if (i%2 === 0) continue;
  console.log('i当前为：' + i);
}
```
上面代码只有在i为奇数时，才会输出i的值。如果i为偶数，则直接进入下一轮循环。

如果存在多重循环，不带参数的break语句和continue语句都只针对最内层循环。
# switch case 语句中的 break 有什么作用
Break 语句它用于跳出 switch() 语句。  
break 语句可用于跳出循环。  
break 语句跳出循环后，会继续执行该循环之后的代码（如果有的话）：
```
for (i=0;i<10;i++)
  {
  if (i==3)
    {
    break;
    }
  x=x + "The number is " + i + "<br>";
  }
```
如果不用break语句终止循环，switch（）语句的内容会全部执行。
# 以下代码的输出结果是? 为什么
```
var a = 1;
var b = 3;
console.log( a+++b );
```
结果为4
```
/*
以上代码可理解为console.log( (a++)+b )或console.log( a+(++b) )而后置递增优先级大于前置递增，则运行结果为console.log( (a++)+b )的结果4
*/
```
# 遍历数组，把数组里的打印数组每一项的平方
```
var arr = [3,4,5]
for(var i = 0;i < arr.length;i++){  
    console.log(arr[i]*arr[i]);
}
```
# 以下代码输出结果是? 为什么 
```
var a = 1, b = 2, c = 3;
var val = typeof a + b || c >0
console.log(val) //num2     运算顺序：(( typeof a ) + b )|| ( c > 0 ),||中第一个值能转换成ture则返回第一个，否则返回第二个

var d = 5;
var data = d ==5 && console.log('bb')
console.log(data)//bb undefined 运算顺序：var data = ((d ==5) && console.log('bb'))，&&中第一个值能转换成false则返回第一个，否则返回第二个，这里返回console.log，结果为undefined

var data2 = d = 0 || console.log('haha')
console.log(data2)
 /* haha undefined  运算顺序：var data2 = (d = (0 || console.log('haha')))，这里返回console.log，结果为undefined
 */
var x = !!"Hello" + (!"world", !!"from here!!");
console.log(x)
/*
2   运算顺序：var x = (!(!"Hello")) + (!(!"from here!!"))如果运算子是对象，先自动转成原始类型的值（即先执行该对象的valueOf方法，如果结果还不是原始类型的值，再执行toString方法；如果对象是Date实例，则先执行toString方法）。
两个运算子都是原始类型的值以后，只要有一个运算子是字符串，则两个运算子都转为字符串，执行字符串连接运算。
否则，两个运算子都转为数值，执行加法运算。
*/
```