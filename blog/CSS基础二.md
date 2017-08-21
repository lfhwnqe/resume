> css基础二

### css中em、rem、vm、vw计算尺寸的方式。
1. 1em＝当前元素字体大小，2em＝当前字体两倍大小
2. 1rem＝当前根元素字体大小，2rem＝当前跟元素字体两杯大小
3. vm分别有vmin和vmax分别是关于视口宽度和高度两者的最大或者最小值
4. width:50vw，这里50vm指视口宽度的50％。height：50vh，这里50vh指占视口高度的50%

### css中颜色的常用写法：
1. 颜色关键字
```
a {
  color: white;
  background-color: blue;
}
```
2. 十六进制值
```
p {
  background-color: #e0b0ff;
}
```
3. RGB
```
p {
  background-color: rgb(224, 176, 255);
}
```
4. HSL
```
p {
  background-color: hsl(276, 100%, 85%);
}
```
5. RGBA & HSLA
```
p {
  background-color: rgb(224, 176, 255, .5);
}
```
```
p {
  background-color: hsla(240, 100%, 50%, 0.5);
}
```
6. currentColor 关键字
###### 表示和当前元素的color一样的颜色
```
 <div class="box">box
    <span class="child">child</span>
  </div>

  <style>
    .box {
      color: red;
    }
    .child {
      border: 4px solid currentColor;
    }

  </style>
```
### css中透明色的表示，透明效果的实现，currentcolor的用法
1. 透明色表示：
```
.box{
    background-color:transparent
}
```
2. 透明效果：设置元素的透明度为0
```
.box{
    opacity:0；
}
```
3. currentColor的用法，如上代码
###### 表示和当前元素的color一样的颜色
```
 <div class="box">box
    <span class="child">child</span>
  </div>

  <style>
    .box {
      color: red;
    }
    .child {
      border: 4px solid currentColor;
    }

  </style>
```
###  css 中calc是什么
calc()从字面我们可以把他理解为一个函数function。其实calc是英文单词calculate(计算)的缩写，是css3的一个新增的功能，用来指定元素的长度。比如说，你可以使用calc()给元素的border、margin、pading、font-size和width等属性设置动态值。为何说是动态值呢?因为我们使用的表达式来得到的值。不过calc()最大的好处就是用在流体布局上，可以通过calc()计算得到元素的宽度
### css3实现垂直居中
```
.box{
    display: flex;
    flex-direction: column;
    justify-content: center;
}
```
### display的值
1. none	此元素不会被显示。
2. block	此元素将显示为块级元素，此元素前后会带有换行符。
3. inline	默认。此元素会被显示为内联元素，元素前后没有换行符。
4. inline-block	行内块元素。（CSS2.1 新增的值）
5. table	此元素会作为块级表格来显示（类似 <table>），表格前后带有换行符。
6. inline-table	此元素会作为内联表格来显示（类似 <table>），表格前后没有换行符。
7. inherit	规定应该从父元素继承 display 属性的值。
### 块级元素和行内元素的特点
1. 块级元素

- HTML（超文本标记语言）中元素大多数都是“块级”元素或行内元素。块级元素占据其父元素（容器）的整个空间，因此创建了一个“块”
- 块级元素标签：<address>、<article>、<ol>、<footer> 、<p>、<form>、<audio>、 <h1>, <h2>, <h3>, <h4>, <h5>, <h6>、<pre>、<dd>、 <ul>、<video>、 <div>、<hr>
2. 行内元素：
- HTML (超文本标记语言) 元素大多数都是行内元素或块级元素。一个行内元素只占据它对应标签的边框所包含的空间。
- 行内元素标签：b, big, i, small, tt
abbr, acronym, cite, code, dfn, em, kbd, strong, samp, var
a, bdo, br, img, map, object, q, script, span, sub, sup
button, input, label, select, textarea

3. 块级元素与行内元素有几个关键区别：
- 格式:
默认情况下，块级元素会新起一行。
- 内容模型:
一般块级元素可以包含行内元素和其他块级元素。这种结构上的包含继承区别可以使块级元素创建比行内元素更”大型“的结构。
### CSS3 box-sizing 属性
box-sizing 属性允许您以特定的方式定义匹配某个区域的特定元素。例：
```
div
{
box-sizing:border-box;
-moz-box-sizing:border-box; /* Firefox */
-webkit-box-sizing:border-box; /* Safari */
width:50%;
float:left;
}
```

- content-box：这是由 CSS2.1 规定的宽度高度行为。
宽度和高度分别应用到元素的内容框。
在宽度和高度之外绘制元素的内边距和边框。
- border-box	：
为元素设定的宽度和高度决定了元素的边框盒。
就是说，为元素指定的任何内边距和边框都将在已设定的宽度和高度内进行绘制。
通过从已设定的宽度和高度分别减去边框和内边距才能得到内容的宽度和高度。
- inherit：	规定应从父元素继承 box-sizing 属性的值。