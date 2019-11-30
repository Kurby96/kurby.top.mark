## Hugo安装

 [下载地址]( https://github.com/gohugoio/hugo/releases ) 

还需要下载 [mercural](https://www.mercurial-scm.org/downloads )  [go](https://golang.org/dl/ ) 

新建E：/Hugo/bin目录，将下载的hugo放到bin目录下

添加E：/Hugo/bin目录到环境变量Path中。效果如下图，如何打开环境变量，不会的自行百度吧。

![](https://raw.githubusercontent.com/BUG-96/hh/master/img/20191128101133.png)

上面可能遇到的问题：

运行 hugo效果不对，尝试着以管理员的方式运行powershell，方法自行百度。

## 创建一个网站

到E:/Hugo/hugo/ 目录下，运行hugo new site blog

 

### 下载主题

```
~ $ cd blog
~/blog $ git init
~/blog $ git submodule add https://github.com/reuixiy/hugo-theme-meme.git themes/meme
```

### 需要更新运行

```
~/blog $ git submodule update --rebase --remote
```

### 初步配置

把`E:\Hugo\blog\themes\meme\config-examples\zh-cn`下的config.toml复制到`E:\Hugo\blog\`下替换掉

### 运行网站 hugo server

1、创建一个新帖子和“关于”页面：

```
〜 / blog $ hugo new “ posts / hello-world.md ”
〜 / blog $ hugo new “ about / _index.md ”
```

2、运行

```
〜 / blog $hugo server-D
```

遇到问题：

![](https://raw.githubusercontent.com/BUG-96/hh/master/img/20191128121358.png)

解决方法：

提示说当前的hugo版本不行，去[hugo官方手册查](https://gohugo.io/troubleshooting/faq/),要下载extended的版本，所以重新下载把它放到/blog/bin目录下，重新运行hugo server即可

在网页上输入  http://localhost:1313/  即可访问你的网页，











 https://oser.space/about/ 





一个小姑娘的博客

 https://www.netlify.com/ 

 https://ipfs.io/ 

![](https://raw.githubusercontent.com/BUG-96/hh/master/img/20191128105010.png)

















 https://study.163.com/course/courseLearn.htm?courseId=1004987024#/learn/video?lessonId=1051323646&courseId=1004987024 



 https://www.gohugo.org/ 