---
title: GitHub提交本地项目
date: 2017-4-6 14:26:57
tags:  GitHub提交本地项目
reward: true
---

## 本文所使用的环境：

* Windows10 64位
* GitHub Desktop(非git for Windows)

### **本文章省略github注册,下载,创建Repository,SSH链接等信息,如有需要请查看本博客其他文章或百度,谢谢!**

# 上传本地项目到github

### 1 创建一个本地项目

这个项目是我自己没事用来练习jQuery插件时使用的,内容并不重要,关键是学习这个上传的方法,
这是[我的jQuery插件库](http://www.jq22.com/),有兴趣可以去看看!

![](http://i2.muimg.com/567571/33efef9552f89314.png)

<!--more-->

### 2 建立本地仓库

创建新仓库的基本指令：

`git init` //把这个目录变成Git可以管理的仓库

`git add README.md` //文件添加到仓库,多个文件时,直接通过空格隔开就行,如 `git add a.md git add b.md`

`git add .` //不但可以跟单一文件，还可以跟通配符，更可以跟目录。一个点(`add 和 . `之间有空格)就把当前目录下所有未追踪的文件全部add了 

`git commit -m "first commit"` //把文件提交到仓库,""当中的内容为对本次提交的说明信息,请尽量写上,以便于后期查看

`git remote add origin git@github.com:ShonLee/Me.git `//关联远程仓库

`git push -u origin master` //把本地库的所有内容推送到远程库上

#### 具体的操作方法

* 进入需要提交的项目根目录,并完成初始化,我的在 `D:\eclipseworkspace\Me`

执行命令:
	
	cd /d/eclipseworkspace/Me
	git init 

![](http://i4.buimg.com/567571/6bc9bb25623c76c6.png)

初始化成功后你会发现项目里多了一个隐藏文件夹 	`.git`

这个目录是Git用来跟踪管理版本库的，没事千万不要手动修改这个目录里面的文件，不然改乱了，就把Git仓库给破坏了。

![](http://i2.muimg.com/567571/945b688b882e1510.png)

* 接着，将所有文件添加到仓库

执行命令:(执行后没有任何信息)

	git add .

![](http://i1.piimg.com/567571/58d3606690ab353d.png)

* 然后，把文件提交到仓库，双引号内是提交注释。

执行命令:

	git commit -m "提交文件说明信息"

![](http://i2.muimg.com/567571/ac6a0a21bd9185cb.png)

---

如此本地仓库建立好了。


### 3 关联github仓库及问题

* 首先在GitHub上新建一个Repository,名称和本地项目的名称一样

![](http://i1.piimg.com/567571/82bb1b32c7118e4c.png)

![](http://i2.muimg.com/567571/10608270c2d3b9eb.png)

执行指令： (执行后没有任何信息)

    git remote add origin git@github.com:ShonLee/Me.git

### 4 上传本地代码


执行指令：(可能会要求 yes/no)

    git push -u origin master

![](http://static.open-open.com/lib/uploadImg/20160203/20160203214852_461.png)


**在使用git 对源代码进行push到gitHub时可能会出错，信息如下**

![](http://i4.buimg.com/567571/819b2f8ea365abcf.png)

出现错误的主要原因是github中的`README.md`文件不在本地代码目录中

![](http://e.hiphotos.baidu.com/exp/w=480/sign=b1b66bf9a186c91708035331f93c70c6/d50735fae6cd7b89ba2db582092442a7d9330e69.jpg)

可以通过如下命令进行代码合并:

	git pull --rebase origin master
	
![](http://i2.muimg.com/567571/e97f5120eaff6019.png)

执行上面代码后可以看到本地代码库中多了README.md文件

![](http://i1.piimg.com/567571/d2a772d14e3eda9f.png)


此时再执行语句 `git push -u origin master`即可完成代码上传到github

![](http://i2.muimg.com/567571/1fc71e0b2f3fdc67.png)


到此，本地代码已经推送到github仓库了，我们现在去githubt仓库看看。

![](http://i4.buimg.com/567571/2f398cbdf1fe121e.png)

咦！奇怪了，我的目录呢？怎么有几个文件夹没有呢?坑爹呢!!!!

注意咯： git是不能管理空的文件夹的，文件夹里必须有文件才能add

当我们在空的文件夹下创建好了文件,再执行指令添加文件->提交文件->推送文件

	git add .
	
	git commit -m "提交test1.html"
	
	git push -u origin master

![借用他人的图片](http://static.open-open.com/lib/uploadImg/20160203/20160203214852_768.png)


然后刷新github，你会看到，原来没有的文件夹出来了。

![借用他人的图片](http://static.open-open.com/lib/uploadImg/20160203/20160203214852_405.png)

>引用文章链接如下:<br>
>[如何解决failed to push some refs to git](http://jingyan.baidu.com/article/f3e34a12a25bc8f5ea65354a.html)<br>
>[github入门到上传本地项目](http://www.open-open.com/lib/view/open1454507333214.html)<br>
>[git commit命令详解](http://blog.csdn.net/killer1989/article/details/46454005)





