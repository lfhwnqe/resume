>本文简介CSS的基础用法

# CSS的引用方式
1.通过 <link> 引入 CSS。
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8" />
  <title>CSS</title>
  <link rel="stylesheet" href="index.css">
</head>
<body>
  <h1>Hello CSS!</h1>
</body>
</html>
```

2. @import的引用方式
_注释:_@import必须写在css中
```
<style>
@import url("index.css");
@import url('index.css');
@import url(index.css);
@import 'custom.css';
@import "common.css";
@import url('landscape.css') screen and (orientation:landscape);

</style>
```
3. 内部引入样式
将 CSS 放在页面的 <style>元素中。
```
<!DOCTYPE html>
<html>
<head>
  <meta charset="UTF-8" />
  <title>CSS</title>
  <style>
    h1 { background: orange; }
  </style>
</head>
<body>
  <h1>Hello CSS!</h1>
</body>
</html>
```

4. 内联样式
不推荐，但在某些情况下很有用。
```
<p style="background: orange; font-size: 24px;">CSS 很 👍<p>
```
# @charset的作用
声明该css文件使用utf-8编码，浏览utf-8编码的任何网页，无论是中文，日文，韩文，都可以正常显示
# @import的作用和使用方法

用于从其他样式表导入样式规则。这些规则必须先于所有其他类型的规则，@charset除外。
用法如下：
```
@import 'custom.css';
```
_注释：_@import必须写在css中

# id 选择器和 class 选择器各自的使用场景
1. id 选择器
id 选择器可以为标有特定 id 的 HTML 元素指定特定的样式。
HTML元素以id属性来设置id选择器,CSS 中 id 选择器以 "#" 来定义。

2. class 选择器
class 选择器用于描述一组元素的样式，class 选择器有别于id选择器，class可以在多个元素中使用。
class 选择器在HTML中以class属性表示, 在 CSS 中，类选择器以一个点"."号显示
#  常用CSS选择器
1.  元素选择器 Element Selectors
2. ID 选择器 ID Selectors
3. 类选择器 Class Selectors
4. *通用选择器 Universal Selector 
5. 属性选择器 Attribute Selectors
6. 伪类选择器 Pseudo-classes
7. 伪元素选择器 Pseudo-elements
8.  组合选择器 Combinators
9. 多个选择器 Multiple Selectors

# 伪类选择器和伪元素
1. 伪类选择器：元素某种状态下，才作为选择器。
```
a:link { ... }
a:visited { ... }
a:hover { ... }
a:active { ... }
li:first-child { ... }
li:last-child { ... }
body :not(p) { ... }
p:not(.warning) { ... }
```
2.  伪元素选择器：
```
::after
::before
::selection
::backdrop
::first-letter
::first-line
::-webkit-input-placeholder
```
# 组合选择器
1. .item+p {color: red} :选中item后的第一个元素p
2. .item~p {color: yellow} :选中item后所有相邻兄弟元素p
3. .item p {color: blue}：选中item下所有元素p
4. p.item {color: blue}：选中p元素下的所有子元素item
5. .item>p{color: blue}：选中item下的直接子元素p
