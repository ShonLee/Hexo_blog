---
title: Xshell通过SSH连接SAE
date: 2017-4-11 08:52:13
tags:  Xshell连接SAE

---

# [Windows环境下通过SSH登录SAE容器虚拟机](http://www.sinacloud.com/home/index/faq_detail/doc_id/173.html) 

新浪云自定义运行环境支持证书通过SSH登录到启动的容器虚拟机，如果你使用的是Windows环境，在完成以下步骤后可以登录。

## 一、生成SSH证书 

### 1、[下载 Git for Windows](https://git-for-windows.github.io/)

使用Git for Windows的ssh-keygen命令，https://git-for-windows.github.io 并完成安装。

### 2、使用ssh-keygen.exe命令

<!--more-->

在任意区域点击右键，选择“Git Bash”，如下图所示：

![](http://www-faq.stor.sinaapp.com/ea577b4172b22d74cb1a.png)

输入命令ssh-keygen.exe，一路“回车”即可，如下图所示：

![](http://www-faq.stor.sinaapp.com/8922d53c882c9714c469.png)

### 3、查看生成的公钥

使用记事本直接打开生成的公钥文件，如图所示：

![](http://www-faq.stor.sinaapp.com/7a07ddc89af64a3b97ef.png)

## 二、上传公钥到新浪云

进入新浪云用户中心，选择左侧“用户信息”，进入“SSH密钥管理”即可上传，如图所示：

![](http://www-faq.stor.sinaapp.com/c19ce60d3a071b0628ec.png)

点击“+创建SSH密钥”，输入一个标题，还有上述用记事本打开的文件公钥文件，如图所示：

![](http://www-faq.stor.sinaapp.com/6a2e19ce2ab11f71ec8b.png)

点击“确定”即可上传完成。

## 三、通过SSH客户端登录到容器

Windows下SSH客户端我们推荐你使用Xshell（也可以使用其他的客户端，我们教程中仅以Xshell为例），Xshell下载地址：https://www.netsarang.com/products/xsh_overview.html ，请下载并完成安装。
### 1、从容器的管理页面获取SSH登录信息

进入应用的容器管理页面，点击“SSH密钥登录”即可查询登录信息，如图所示：

![](http://www-faq.stor.sinaapp.com/98d42312ddbe7d976c59.png)

端口为：60022

用户名为：您的应用名（比如`douyu1`）。

### 2、通过Xshell登录

点击“文件” -> "新建会话"，主机处填写“ssh.sinacloud.com”，端口处填写“60022”，如图所示：

![](http://www-faq.stor.sinaapp.com/b889c6753d43bfc97eb4.png)

点击“用户身份验证”配置登录信息为：

方法选择：`Public key`

用户名为：应用的二级域名前缀

用户密钥：选择刚生成的私钥文件，一般文件名叫id_rsa，通常路径在 `C:\Users\你的windows用户名\.ssh\ `这个目录下，如下图所示：

![](http://www-faq.stor.sinaapp.com/82be13e65669c9f70615.png)

点击确定即可登录容器，登录成功后如下：

![](http://www-faq.stor.sinaapp.com/d862ace41f74d4085751.png)


### ３、接下来，我们就可以使用命令做一系列操作了。

3-1：cd 是进入下一级目录命令

　　例如：`cd /folder1/folder2/folder3`

 3-2：复制文件：cp -r 【需要复制的文件名】/ 【复制成的文件名】

　　例如：复制fileName 重命名为fileName1

　　`cp -r fileName/ fileName1`

 3-3：netstat是查看端口是否呗占用

　　例如：`netstat -app|grep 10086`

 3-4：编辑文件：vim

　　例如：`vim server.xml`

 3-5：按住 

	i键进入编辑模式
	编辑完 按住Esc取消编辑
	输入 :wq! 保存
	　　：q! 是不保存

 3-6：recover

 3-7：查看日志详情：

	①直接打开：tail -f 【日志文件名】
	②打开200行：tail -f -n200 【日志文件名】
	
	　　例如：查看日志详情
	　　tail -f -n200 xxxxx.log

 3-8：telnet 地址 端口

### 4、进程查看，杀进程，起进程

 4-1：`ps -ef|grep ServerRun`   查看运行的进程

 4-2：杀进程
	
	   使用kill命令结束进程：kill xxx
	   常用：kill －9 324
	   Linux下还提供了一个killall命令，可以直接使用进程的名字而不是进程标识号，
	   例如：# killall -9 NAME

 4-3：启动进程

　　进入到进程的目录下 执行 ./进程名字

　　例如：
	![](http://images2015.cnblogs.com/blog/1018407/201704/1018407-20170406102011003-2130686863.png)