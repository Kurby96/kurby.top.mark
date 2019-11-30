+++
title = "picGo工具使用说明"
tags = ["alone"]
date = "2018-08-26T14:13:56+08:00"
slug = "you-are-not-a-fish"
comments = true
+++

#### picGo工具使用说明

先说一下背景吧，本人写makedown喜欢在本地写，使用的是typora，[下载地址]( https://www.typora.io/ ),有时候截图直接粘贴到typora上了，typora用的是本地的路径，当传到csdn或者其他上面，图片的链接就不见了，很是捉鸡，所以上网上查查有没有解决方案。遇到了picGo，很是欣喜。这里说一下使用方法吧。

教程链接： [https://picgo.github.io/PicGo-Doc/zh/guide/config.html#github%E5%9B%BE%E5%BA%8A](https://picgo.github.io/PicGo-Doc/zh/guide/config.html#github图床) 

教程看着蛮复杂的，我这里简化一下。

##### 1、下载应用

应用下载地址： [https://github.com/Molunerfinn/PicGo/releases]( https://github.com/Molunerfinn/PicGo/releases )

 macOS用户请下载最新版本的`dmg`文件，windows用户请下载最新版本的`exe`文件，linux用户请下载`AppImage`文件 。

下好之后，直接安装就行。

##### 2、配置环境变量

 前提: 先安装node.js，版本要大于8,然后配置环境。

先找到环境变量，不知道在哪的百度搜windows环境变量怎么找，点击环境变量，点击Path，点击编辑。

![](https://raw.githubusercontent.com/BUG-96/PicStore/master//img20191120161238.png)

然后新建，把 %APPDATA%\picgo\data.json 粘贴到上面。重启使环境变量生效。

![](https://raw.githubusercontent.com/BUG-96/PicStore/master//img20191120161449.png)



##### 3、一些基本操作

这些操作就看上面的文档，包括上传啊，相册啊，什么的。

##### 4、图床设置  (github方式)

1、一个仓库，记录一下仓库地址。

2、 生成一个token用于PicGo操作你的仓库： 

 访问：https://github.com/settings/tokens 

 然后点击`Generate new token`。 

![](https://raw.githubusercontent.com/BUG-96/PicStore/master//img20191120162506.png)

 把repo的勾打上即可。然后翻到页面最底部，点击`Generate token`的绿色按钮生成token。 

![](https://raw.githubusercontent.com/BUG-96/PicStore/master//img20191120162609.png)

 **注意：**这个token生成后只会显示一次！你要把这个token复制一下存到其他地方以备以后要用。 

![](https://raw.githubusercontent.com/BUG-96/PicStore/master//img20191120162900.png)

3、 配置PicGo 

 **注意：**仓库名的格式是`用户名/仓库`，比如我创建了一个叫做`test`的仓库，在PicGo里我要设定的仓库名就是`Molunerfinn/test`。一般我们选择`master`分支即可。然后记得点击确定以生效，然后可以点击`设为默认图床`来确保上传的图床是GitHub。 

![](https://raw.githubusercontent.com/BUG-96/PicStore/master//img20191120163040.png)

设定自定义域名，这个是你上传图片到Github上，picGo会给你一个链接，已经复制到剪切板上了，这个就是配置剪切板上路径的。

这个路径的前缀你可以打开github上的图片，右键-  `在新标签页中打开图片(i)`,查看前面的路径

![](https://raw.githubusercontent.com/BUG-96/PicStore/master//img20191120170621.png)

得到的路径就是： https://raw.githubusercontent.com/BUG-96/PicStore/master 把这个填到设置自定义域名中即可。

##### 5、下面就是一些自己的配置，参考文档就行了。



