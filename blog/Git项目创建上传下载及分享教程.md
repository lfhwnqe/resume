####创建git项
本文章分享如何在GitHub上创建一个新的项目，并且通过linux命令行工具在电脑上下载这个项目并且进行编辑。然后上传到GitHub服务器。并且以链接的形式发布到网上
需要注册GitHub，电脑安装linux命令行工具git_bash
###### （一）项目建立

![打开GitHub网站，创建一个New repository](http://upload-images.jianshu.io/upload_images/6992621-d4ba604e995a4d23.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###### （二）项目设置


![填写项目名，做好设置，然后点击Create repository 创建项目](http://upload-images.jianshu.io/upload_images/6992621-b332dea9d084923f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


####项目下载
######（一）拷贝地址

![点击Clone or download，并拷贝ssh地址](http://upload-images.jianshu.io/upload_images/6992621-eee192d2ab6f2b68.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

###### （二）下载项目



![运行git_bash克隆上一步创建的项目下载地址](http://upload-images.jianshu.io/upload_images/6992621-84030eb61be3230c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![克隆成功后会显示done。如上图 ](http://upload-images.jianshu.io/upload_images/6992621-34b75d9720db888c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

######（三）报错
 
![如果输入时出现如下报错。是因为没有设置公钥。需要设置公钥后才能下载项目 ](http://upload-images.jianshu.io/upload_images/6992621-d5b0c48ae0d6df9a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
######（四）报错解决

![解决上一步报错，需要设置公钥。方法如上图所示依次排列：
进入设置](http://upload-images.jianshu.io/upload_images/6992621-f944f11832c64310.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![点开公钥设置并点击创建公钥向导](http://upload-images.jianshu.io/upload_images/6992621-83e18b3f47bb187b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![找到公钥创建向导，点击进入如何创建公钥](http://upload-images.jianshu.io/upload_images/6992621-511fc3bc2a59ae76.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![按照顺序依次操作](http://upload-images.jianshu.io/upload_images/6992621-992cde7f06b850e5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![此处输入你的GitHub邮箱](http://upload-images.jianshu.io/upload_images/6992621-42ad69d66826cb70.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![输入命令后，一直按回车，最后变成这个样子。在~/.ssh目录下生产了公钥id_rsa.pub](http://upload-images.jianshu.io/upload_images/6992621-4d25cdef732bbe0c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![用cat命令显示这个公钥，然后把它的内容复制到剪贴板](http://upload-images.jianshu.io/upload_images/6992621-72653990004cb170.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



![再次进入GitHub的公钥设置中，粘贴刚刚拷贝的数据并保存。！！！！注意！！！！
在此处设置好公钥后，以后下载上传项目就不需要再次设置公钥。](http://upload-images.jianshu.io/upload_images/6992621-c1838e80e747f540.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




######（五）从新下载项目

![再次输入clone命令，这次成功下载项目](http://upload-images.jianshu.io/upload_images/6992621-18bb35de2effe552.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

####项目编辑
######（一）项目编辑

![拷贝成功，使用命令行命令进入下载的项目文件](http://upload-images.jianshu.io/upload_images/6992621-0bb1764f61cd5c5b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![使用命令行创建index.html](http://upload-images.jianshu.io/upload_images/6992621-10b5feef209cd2cf.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


######（二）项目上传

![输入提交命令，出现一串代码。global user.email "you@example.com"等。git服务器需要我们提供我们的git邮箱和id用来确定我们的身份](http://upload-images.jianshu.io/upload_images/6992621-a7937ac50544d35e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)




![根据提示输入命令，依次填入我的GitHub邮箱和id。回车后再次上传，显示上传成功。然后将保存在本地的文件push到GitHub远程库](http://upload-images.jianshu.io/upload_images/6992621-1af1b49fc61e9b08.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![在GitHub刷新，看到我们刚刚上传的文件index.html文件上传成功](http://upload-images.jianshu.io/upload_images/6992621-01d087807fe63a3e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


####项目分享



![在项目根目录下点击Settings，准备分享我们的项目](http://upload-images.jianshu.io/upload_images/6992621-4446589d16df94b5.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![跟着上一步，下翻，依图设置，然后点击save](http://upload-images.jianshu.io/upload_images/6992621-864e5cd754812445.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![跟着上一步，出现链接。大家就可以通过这个链接访问到我们创建的项目Project了](http://upload-images.jianshu.io/upload_images/6992621-55a8041cc1d3312c.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


![线上预览项目，此次因为项目为内没有编辑内容，显示为空白](http://upload-images.jianshu.io/upload_images/6992621-ac745fdc6dbab622.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)