---
title: Java环境,IDE,Project
date: 2017-4-16 10:12:31
tags:  Java环境,IDE,Project
reward: true
---

# Java环境,IDE,Project

---

### <font color="red">一 : JAVA环境配置</font>

#### 1: 在官网下载自己系统所需的JDK及相关的版本

![](http://i2.muimg.com/567571/d0d91eb0092c0192.png)

#### 2: 下载后双击文件运行安装,记住自己的安装地址，后面是要用到安装地址的

<!--more-->

![](http://i2.muimg.com/567571/614b96664d0862fc.png)

#### 3: 安装完成后配置环境,首先找到计算机的属性页面,点击高级系统设置.如图:

![](http://i4.buimg.com/567571/cbd7b2c7c44296c6.png)

![](http://i2.muimg.com/567571/7f6b728dd942de04.png)

#### 4: 选择【新建系统变量】--弹出“新建系统变量”对话框，在“变量名”文本框输入“JAVA_HOME”,在“变量值”文本框输入JDK的安装路径，单击“确定”按钮，如图：

![](http://i2.muimg.com/567571/cd9eae271a209b75.png)

#### 5: 在“系统变量”选项区域中查看PATH变量，如果不存在，则新建变量 PATH，否则选中该变量，单击“编辑”按钮，在“变量值”文本框的起始位置添加`“%JAVA_HOME%\bin;%JAVA_HOME%\jre\bin;”`或者是直接`“%JAVA_HOME%\bin;”`，单击确定按钮，如图：

![](http://i4.buimg.com/567571/c2a7d230fc19e189.png)

#### 6: 在“系统变量”选项区域中查看CLASSPATH 变量，如果不存在，则新建变量`CLASSPATH`，否则选中该变量，单击“编辑”按钮，在“变量值”文本框的起始位置添加`“.;%JAVA_HOME%\lib\dt.jar;%JAVA_HOME%\lib\tools.jar;”`。如图：

![](http://i2.muimg.com/567571/bef0eb72baedbe73.png)

#### 7: 打开命令提示符

	输入  java
	输入  javac
	输入  java -version

如果显示如图所示，安装成功

![](http://i2.muimg.com/567571/712c65b0d5364c5e.png)

![](http://i1.piimg.com/567571/9cbff8fd271e447f.png)

![](http://i2.muimg.com/567571/9e06e6366a81d98a.png)

---

### <font color="red">二 : Eclipse下载,插件及配置</font>

官网下载地址:[https://www.eclipse.org/downloads/](https://www.eclipse.org/downloads/)


#### 1: 反编译插件

在实际的开发中几乎都会使用到一些框架来辅助项目的开发工作，对于一些框架的代码我们总怀有一些好奇之心，想一探究竟，有源码当然更好了，对于有些 JAR包中的代码我们就需要利用反编译工具来看一下了:

1.1: Eclipse的版本信息

![](http://i1.piimg.com/567571/6af27ef691df942f.png)

1.2: Help——Eclipse Marketplace

![](http://i1.piimg.com/567571/a7fa968c8cfb54e9.png)

1.3: 输入 `Decompiler`或者`反编译` 搜索并安装此插件

![](http://i2.muimg.com/567571/6a7b7a9031efcc29.png)

![](http://i4.buimg.com/567571/287c41235af604c3.png)

1.4: 这里有几种不同的反编译插件工具的选择，默认就好..

![](http://i4.buimg.com/567571/391dbd9c868a0161.png)

1.5: 然后点击`同意` `确认`..... 重启即生效

![](http://i4.buimg.com/567571/3cb163282071b641.png)

---

#### 2: Eclipse下web项目部署出错的问题的解决

2.1: 项目名称上右键选择properties（属性）

2.2: 进入项目的属性界面点击java build path 看下AB两次是否有错误

![](http://i4.buimg.com/567571/fe936936c5c75347.png)

2.3: 如果A处有错无会出现有关servlet的java错误；如果是B处有错误则会出现常规java类找不到类的错误，即是无法编译的原因，因为没有jre的环境

2.4: A处出错误的解决办法是添加一个server，luna版本的eclipse可以自动将server的运行环境添加到项目的运行环境中去，稍低版本的eclipse需要自己添加servlet-api的jar包。

2.5: B处出现错误的话则双击JRE System library添加java的运行环境如下图所示

![](http://i4.buimg.com/567571/b2a11d5ce93e934b.png)

2.6: 如果alternate JRE要是没有的话，可以点击Installed JREs选择自己安装的JRE环境，如下图所示

![](http://i2.muimg.com/567571/d95f68556d73e01b.png)

2.7: 如果按以上步骤操作完成，还是在java类中出现错误的话，则可能是因为JRE版本的问题所致。可检测一下下图地方是否和你刚才所配的jre环境一致。

![](http://i4.buimg.com/567571/d16b91f72c485ff8.png)

2.8: 按着上述步骤应该可以解决在eclipse下配置web项目的一些问题，如果还是有错的话，则考虑项目本身代码的错误

--- 

#### 3: Maven配置及报错解决

3.1: Maven的下载:[http://maven.apache.org/download.cgi](http://maven.apache.org/download.cgi)

3.2: 配置maven集成包`one214_maven`的路径

打开`maven`的`settings.xml`文件(路径:`D:\apache-maven-3.3.3\conf\`)进行如下设置:

![](http://i4.buimg.com/567571/c931a4c9f069f8d1.png)

3.3: 环境配置

3.3.1 打开电脑环境配置选项:

![](http://i4.buimg.com/567571/cbd7b2c7c44296c6.png)

![](http://i2.muimg.com/567571/7f6b728dd942de04.png)

3.3.2 maven环境配置

![](http://i4.buimg.com/567571/65f60b33aba1d592.png)

![](http://i4.buimg.com/567571/bb4d3579b370ce79.png)

3.3.3 maven配置完成测试(CMD中测试)

	CMD
	MVN -V

![](http://i1.piimg.com/567571/b3b77b5fcb14f839.png)

#### 4: eclipse设置文件的默认打开方式

具体方法如下，我直接上图了：

![](http://dl2.iteye.com/upload/attachment/0102/4302/c14da00e-c87f-3194-98df-f18fd07a71eb.jpg)

![](http://dl2.iteye.com/upload/attachment/0102/4304/fac02cda-ca29-340b-acd5-b96eaae49f9a.jpg)

#### 5: java、HTML、JavaScript、JSP文件代码自动提示

5.1: java自动代码提示:
`Window -> Preferences -> Java -> Editor -> Content Assist -> Auto Activation`

![](http://images.cnitblog.com/i/19318/201403/061810532842824.jpg)

delay是自动弹出提示框的延时时间，我们可以修改成100毫秒；triggers这里默认是"."，只要加上"abcdefghijklmnopqrstuvwxyz"或者"abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"，嘿嘿！这下就能做到输入每个字母都能提示啦：

![](http://images.cnitblog.com/i/19318/201403/061816241908862.jpg)

5.2: JavaScript自动代码提示:

`Window -> Preferences -> JavaScript-> Editor -> Content Assist -> Auto-Activation`

![](http://images.cnitblog.com/i/19318/201403/261755189999973.jpg)

5.3: HTML(JSP)自动代码提示:

`Window -> Preferences -> Web -> HTML Files -> Editor -> Content Assist -> Auto-Activation`

![](http://images.cnitblog.com/i/19318/201403/261757273589891.jpg)

保存后，我们再来输入看看，感觉真是不错呀：

![](http://images.cnitblog.com/i/19318/201403/261803398273001.jpg)

#### 6: 常用快捷键

	Ctrl+1 快速修复(最经典的快捷键,就不用多说了)
	Ctrl+2+L 自动生成返回值
	Ctrl+D: 删除当前行 
	Ctrl+Alt+↓ 复制当前行到下一行(复制增加)
	Ctrl+Alt+↑ 复制当前行到上一行(复制增加)
	Alt+↓ 当前行和下面一行交互位置(特别实用,可以省去先剪切,再粘贴了)
	Alt+↑ 当前行和上面一行交互位置(同上)
	Alt+← 前一个编辑的页面
	Alt+→ 下一个编辑的页面(当然是针对上面那条来说了)
	Alt+Enter 显示当前选择资源(工程,or 文件 or文件)的属性
	Shift+Enter 在当前行的下一行插入空行(这时鼠标可以在当前行的任一位置,不一定是最后)
	Shift+Ctrl+Enter 在当前行插入空行(原理同上条)
	Ctrl+Q 定位到最后编辑的地方
	Ctrl+L 定位在某行 (对于程序超过100的人就有福音了)
	Ctrl+M 最大化当前的Edit或View (再按则反之)
	Ctrl+/ 注释当前行,再按则取消注释
	Ctrl+O 快速显示 OutLine,可以显示当前文件的所有属性和方法。
	Ctrl+T 快速显示当前类的继承结构
	Ctrl+W 关闭当前Editer文件
	Ctrl+K 参照选中的Word快速定位到下一个
	Ctrl+E 快速显示当前Editer的下拉列表(如果当前页面没有显示的用黑体表示)
	Ctrl+/(小键盘) 折叠当前类中的所有代码
	Ctrl+×(小键盘) 展开当前类中的所有代码
	Ctrl+Space 代码助手完成一些代码的插入(但一般和输入法有冲突,可以修改输入法的热键,也可以暂用Alt+/来代替)
	Ctrl+Shift+E 显示管理当前打开的所有的View的管理器(可以选择关闭,激活等操作)
	Ctrl+J 正向增量查找(按下Ctrl+J后,你所输入的每个字母编辑器都提供快速匹配定位到某个单词,如果没有,则在stutes line中显示没有找到了,查一个单词时,特别实用,这个功能Idea两年前就有了)
	Ctrl+Shift+W 关闭所有文件
	Ctrl+Shift+J 反向增量查找(和上条相同,只不过是从后往前查)
	Ctrl+Shift+F4 关闭所有打开的Editer
	Ctrl+Shift+X 把当前选中的文本全部变为小写
	Ctrl+Shift+Y 把当前选中的文本全部变为小写
	Ctrl+Shift+G,找出调用某个方法的所有类
	Ctrl+Shift+F 格式化当前代码
	Ctrl+Shift+P 定位到对于的匹配符(譬如{}) (从前面定位后面时,光标要在匹配符里面,后面到前面,则反之)


	Java编辑器 打开结构 Ctrl+F3 
	全局 打开类型 Ctrl+Shift+T 
	全局 打开类型层次结构 F4 
	全局 打开声明 F3 
	全局 打开外部javadoc Shift+F2 
	全局 打开资源 Ctrl+Shift+R 
	Java编辑器 格式化 Ctrl+Shift+F 
	Java编辑器 取消注释 Ctrl+\ 
	Java编辑器 注释 Ctrl+/ 
	Java编辑器 添加导入 Ctrl+Shift+M 
	Java编辑器 组织导入 Ctrl+Shift+O 


---

### <font color="blue">三 : Maven_web项目导入eclipse出错</font>

#### 1: 导入maven_web项目(过程略),等待`工作空间`构建完成

#### 2: 部署到tomcat	

![](http://i4.buimg.com/567571/c21bd951aa24291e.png)

![](http://i4.buimg.com/567571/6cff1809cf33d626.png)

#### 3: 配置maven仓库

  Windows ---> Preferences

![](http://i4.buimg.com/567571/df3c6726fe7807cc.png)







