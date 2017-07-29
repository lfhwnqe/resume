>本文分享form表单的一些使用方法
### post 和 get 方式提交数据的区别：
1. 提交方式区别
  GET请求的数据会附在URL之后，以？分割URL和传输数据参数之间以&相接。如果是数据，原样发送，如果是中文/其他字符，则用BAS64加密。
 POST把提交的数据则放在HTTP包的包体中。 
2. 提交数据大小
 GET提交的长度和URL长度有直接关系，URL不存在参数上限的问题，HTTP协议规范没有对URL长度进行限制这个限制是特定的浏览器及服务器对它的限制。IE对URL长度的限制是2083字节（2K+35）。对于其他 浏览器，如Netscape、FireFox等，理论上没有长度限制，其限制取决于操作系统的支持。
 理论上POST是没有大小限制的，HTTP协议规范也没有进行大小限制，起限制作用的是服务器的处理程序的处理能力。
3. 安全性对比
 POST比GET的安全性高。通过GET提交数据，用户名密码会以明文的形式出现在URL上，（1）登录页面可能被浏览器缓存，（2）其他人查看浏览器历史记录，那么别人就可以拿到你的账号和密码了，（3）使用GET提交数据可能会造成CSRF攻击。
4. 总结
 Get是向服务器发索取数据的一种请求，而Post是向服务器提交数据的一种请求，在FORM（表单）中Method默认是"Get"，实质上Get和Post只是收发机制不同。

### input标签中name的作用
  name属性规定input元素的名称。name属性只用于提交到服务器后的表单数据进行标识，或者在客户端通过JavaScript引用表单数据。

_注释_：只有设置了name属性的表单元素才能在提交表单时传递它们的值。

### radio分组
要给radio分组，在radio标签内加入name属性即可。同意name属性即为一组如下
```
<audio controls>
  <source src="viper.mp3" type="audio/mp3" name="radio1">
  <source src="viper.ogg" type="audio/ogg" name="radio1">
  <source src="song.mp3 type="audio/mp3" name="radio2">
  <p>你的浏览器不支持 HTML5 音频。</p>
</audio>
```
两个radio1标签为一组

### placeholder属性的作用

  placeholder 属性提供可描述输入字段预期值的提示信息。
  该提示会在输入字段为空时显示，并会在字段获得焦点时消失。

_注释_：placeholder 属性适用于以下的 <input> 类型：text, search, url, telephone, email 以及 password。

_注释_: placeholder 属性是 HTML5 中的新属性。
