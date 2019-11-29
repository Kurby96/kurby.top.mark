# 廖雪峰‘s Git

[TOC]

## Git的诞生

先是因为CVS、SVN都是付费的，不符合开源精神，后来 BitKeeper 的东家BitMover公司出于人道主义精神，授权Linux社区免费使用这个版本控制系统。 后来有个Linux的牛人把BitMove给破解了，所以LinuX无法免费使用了，Linus大佬用了两周时间用C写出了一个分布式的版本控制系统Git，此乃神人也~

## Git的安装

[Git下载](https://git-scm.com/download/)，可以自己根据自己的操作系统选择，我为了方便用的是windows的，

安装完成后，运行git bash ，弹出一个命令行的东西，说明安装成功了。

```go
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

创建版本库

创建一个文件夹、git init 把当前目录设置成Git可以管理的仓库：

```
$ mkdir learngit
$ cd learngit
$ git init
```

 如果你没有看到`.git`目录，那是因为这个目录默认是隐藏的，用`ls -ah`命令就可以看见。 

## 上传文件放到Git仓库 

###  git add && git commit

第 一步，用命令`git add`告诉Git，把文件添加到仓库： 

```
$ git add readme.txt
```

 第二步，用命令`git commit`告诉Git，把文件提交到仓库： 

![](https://raw.githubusercontent.com/BUG-96/hh/master/img/20191127160301.png)



简单解释一下`git commit`命令，`-m`后面输入的是本次提交的说明，可以输入任意内容，当然最好是有意义的，这样你就能从历史记录里方便地找到改动记录。

为什么Git添加文件需要`add`，`commit`一共两步呢？因为`commit`可以一次提交很多文件，所以你可以多次`add`不同的文件，比如：

```
$ git add file1.txt
$ git add file2.txt file3.txt
$ git commit -m "add 3 files."
```

我们已经成功地添加并提交了一个readme.txt文件，现在，是时候继续工作了，于是，我们继续修改readme.txt文件，改成如下内容：

```
Git is a distributed version control system.
Git is free software.
```

### git status

现在，运行`git status`命令看看结果：

```
$ git status
On branch master
Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git checkout -- <file>..." to discard changes in working directory)

	modified:   readme.txt

no changes added to commit (use "git add" and/or "git commit -a")
```

`git status`命令可以让我们时刻掌握仓库当前的状态，上面的命令输出告诉我们，`readme.txt`被修改过了，但还没有准备提交的修改。

### git diff

虽然Git告诉我们`readme.txt`被修改了，但如果能看看具体修改了什么内容，自然是很好的。比如你休假两周从国外回来，第一天上班时，已经记不清上次怎么修改的`readme.txt`，所以，需要用`git diff`这个命令看看：

```
$ git diff readme.txt 
diff --git a/readme.txt b/readme.txt
index 46d49bf..9247db6 100644
--- a/readme.txt
+++ b/readme.txt
@@ -1,2 +1,2 @@
-Git is a version control system.
+Git is a distributed version control system.
 Git is free software.
```

`git diff`顾名思义就是查看difference，显示的格式正是Unix通用的diff格式，可以从上面的命令输出看到，我们在第一行添加了一个`distributed`单词。

知道了对`readme.txt`作了什么修改后，再把它提交到仓库就放心多了，提交修改和提交新文件是一样的两步，第一步是`git add`：

```
$ git add readme.txt
```

同样没有任何输出。在执行第二步`git commit`之前，我们再运行`git status`看看当前仓库的状态：

```
$ git status
On branch master
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

	modified:   readme.txt
```

`git status`告诉我们，将要被提交的修改包括`readme.txt`，下一步，就可以放心地提交了：

```
$ git commit -m "add distributed"
[master e475afc] add distributed
 1 file changed, 1 insertion(+), 1 deletion(-)
```

提交后，我们再用`git status`命令看看仓库的当前状态：

```
$ git status
On branch master
nothing to commit, working tree clean
```

### git log

查看版本控制的记录

![](https://raw.githubusercontent.com/BUG-96/hh/master/img/20191127162528.png)



git log --pretty=oneline  就查看一行有那些版本

上图中的(HEAD ->master)表示的就是当前使用的版本

 首先，Git必须知道当前版本是哪个版本，在Git中，用`HEAD`表示当前版本，也就是最新的提交`1094adb...`（注意我的提交ID和你的肯定不一样），上一个版本就是`HEAD^`，上上一个版本就是`HEAD^^`，当然往上100个版本写100个`^`比较容易数不过来，所以写成`HEAD~100`。 

想要回到add something 要用

git reset --hard HEAD^ 表示要回到上一个版本

![](https://raw.githubusercontent.com/BUG-96/hh/master/img/20191127163042.png)

图中可以看到版本变成了 add something 的版本了

但是要注意的是咱们执行git log 只有2个版本了，add lpl的版本不见了！咋办很慌啊？

### git reflog

可以记录咱们的git reset 的所有操作  ，我们只有git reset --hard xxx 就行了。

![](https://raw.githubusercontent.com/BUG-96/hh/master/img/20191127163717.png)



### git checkout -- 

撤销更改的文件。<font color=red> 注意：</font> 这里和git checkout 不一样 有 --

可以撤销已经git add file和git checkout -- file的文件回到之前的状态

<font color=red> 注意：</font> 还可以用 git reset HEAD readme.txt 功能和git checkout -- 一样的。

### git rm xxx

添加了一个文件到版本库之后，如果这个文件删除了，那么git status的时候就会显示这个文件已经删除了，如果不要这个文件了，可以 git rm xxx 从本地版本库中删除xxx文件。

![](https://raw.githubusercontent.com/BUG-96/hh/master/img/20191127173142.png)



 https://www.liaoxuefeng.com/wiki/896043488029600/900002180232448  学到

















































































本博客参考廖雪峰git教程：[廖老师网站官网](https://www.liaoxuefeng.com/)，非常感谢廖老师的分享。