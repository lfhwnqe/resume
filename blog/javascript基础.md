# javascript历史
##### Nombas 和 ScriptEase  
大概在 1992 年，一家称作 Nombas 的公司开发了一种叫做 C 减减（C-minus-minus，简称 Cmm）的嵌入式脚本语言。Cmm 背后的理念很简单：一个足够强大可以替代宏操作（macro）的脚本语言，同时保持与 C （和 C ++）足够的相似性，以便开发人员能很快学会。这个脚本语言捆绑在一个叫做 CEnvi 的共享软件中，它首次向开发人员展示了这种语言的威力。
Nombas 最终把 Cmm 的名字改成了 ScriptEase，原因是后面的部分（mm）听起来过于消极，同时字母 C “令人害怕”。
现在 ScriptEase 已经成为了 Nombas 产品背后的主要驱动力。
##### Netscape 发明了 JavaScript
当 Netscape Navigator 崭露头角时，Nombas 开发了一个可以嵌入网页中的 CEnvi 的版本。这些早期的试验被称为 Espresso Page（浓咖啡般的页面），它们代表了第一个在万维网上使用的客户端语言。而 Nombas 丝毫没有料到它的理念将会成为万维网的一块重要基石。
当网上冲浪越来越流行时，对于开发客户端脚本的需求也逐渐增大。此时，大部分因特网用户还仅仅通过 28.8 kbit/s 的调制解调器连接到网络，即便这时网页已经不断地变得更大和更复杂。而更加加剧用户痛苦的是，仅仅为了简单的表单有效性验证，就要与服务器进行多次地往返交互。设想一下，用户填完一个表单，点击提交按钮，等待了 30 秒的处理后，看到的却是一条告诉你忘记填写一个必要的字段。
那时正处于技术革新最前沿的 Netscape，开始认真考虑开发一种客户端脚本语言来解决简单的处理问题。
当时工作于 Netscape 的 Brendan Eich，开始着手为即将在 1995 年发行的 Netscape Navigator 2.0 开发一个称之为 LiveScript 的脚本语言，当时的目的是在浏览器和服务器（本来要叫它 LiveWire）端使用它。Netscape 与 Sun 及时完成 LiveScript 实现。
就在 Netscape Navigator 2.0 即将正式发布前，Netscape 将其更名为 JavaScript，目的是为了利用 Java 这个因特网时髦词汇。Netscape 的赌注最终得到回报，JavaScript 从此变成了因特网的必备组件。
##### 三足鼎立   
因为 JavaScript 1.0 如此成功，Netscape 在 Netscape Navigator 3.0 中发布了 1.1 版。恰巧那个时候，微软决定进军浏览器，发布了 IE 3.0 并搭载了一个 JavaScript 的克隆版，叫做 JScript（这样命名是为了避免与 Netscape 潜在的许可纠纷）。微软步入 Web 浏览器领域的这重要一步虽然令其声名狼藉，但也成为 JavaScript 语言发展过程中的重要一步。
在微软进入后，有 3 种不同的 JavaScript 版本同时存在：Netscape Navigator 3.0 中的 JavaScript、IE 中的 JScript 以及 CEnvi 中的 ScriptEase。与 C 和其他编程语言不同的是，JavaScript 并没有一个标准来统一其语法或特性，而这 3 种不同的版本恰恰突出了这个问题。随着业界担心的增加，这个语言的标准化显然已经势在必行。
##### 标准化  
1997 年，JavaScript 1.1 作为一个草案提交给欧洲计算机制造商协会（ECMA）。第 39 技术委员会（TC39）被委派来“标准化一个通用、跨平台、中立于厂商的脚本语言的语法和语义”(http://www.ecma-international.org/memento/TC39.htm)。由来自 Netscape、Sun、微软、Borland 和其他一些对脚本编程感兴趣的公司的程序员组成的 TC39 锤炼出了 ECMA-262，该标准定义了名为 ECMAScript 的全新脚本语言。
在接下来的几年里，国际标准化组织及国际电工委员会（ISO/IEC）也采纳 ECMAScript 作为标准（ISO/IEC-16262）。从此，Web 浏览器就开始努力（虽然有着不同的程度的成功和失败）将 ECMAScript 作为 JavaScript 实现的基础。
# 浏览器的渲染机制  
- 获取 HTML 文档及样式表文件
- 解析成对应的树形数据结构  
  - DOM tree  
  - CSSOM tree
- 计算可见节点形成 render tree
- 计算 DOM 的形状及位置进行布局
- 将每个节点转化为实际像素绘制到视口上（栅格化）  
  
render tree（页面上所显示的最终结果）是由 DOM tree（开发工具中所显示的 HTML 所定义的内容结构）与 CSSOM tree（样式表所定义的规则结构）合并并剔除不可见的节点所形成的，其中不包含如下节点:
- 本身不可见的
  - <html>
  - <head>
  - <meta>
  - <link>
  - <style>
  - <script>
- 设置了 display: none; 样式的
# css样式javascript样式在html中的位置  
CSS文件的引入位置放在头部（<head>标签内部）
将js文件的引入位置放在底部（</body>前面）
# 白屏&FOUC (Flash of Unstyled Content) 无样式内容闪烁  
- 不同的浏览器对于CSS和HTML的处理方式不同，有的是等待CSS加载完成之后，对HTML元素进行渲染和展示（白屏问题）。有的是先对HTML元素进行展示，然后等待CSS加载完成之后重新对样式进行修改（FOUC无样式内容闪烁）  
- 如果把js文件放在头部，脚本会阻塞后面内容的呈现，脚本会阻塞其后组件的下载，出现白屏问题。
# repaint和 reflow的概念
1. repaint:不改变位置的更改样式操作
2. reflow:改变位置的的更改样式操作
- reflow和repaint都需要运算。所有需要优化尽量减少运算量。（如：减少DOM元素直接操作、）
# 如何异步加载脚本
1. repaint:不改变位置的更改样式操作
2. reflow:改变位置的的更改样式操作
- reflow和repaint都需要运算。所有需要优化尽量减少运算量。（如：减少DOM元素直接操作、）
# js的加载会阻塞后面元素的加载
- 有必要使用异步加载，可以设置加载数据
```
<script src="script.js"></script>
<script defer src="script.js"></script>
<script async src="script.js"></script>
```
- defer:脚本延迟到文档解析和显示后执行，有顺序
- async:不保证顺序
- 没有 defer 或 async，浏览器会立即加载并执行指定的脚本，“立即”指的是在渲染该 script 标签之下的文档元素之前，也就是说不等待后续载入的文档元素，读到就加载并执行。