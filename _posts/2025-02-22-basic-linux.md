---
layout: post
title: linux 笔记
categories: [basic,Linux]
description: linux 初识
keywords: basic,Linux
---
linux 简单上手

Linux 英文解释为 Linux is not Unix,Linux在计算机界的地位就不必多说了，这篇文章是一篇简单入门篇，看Linux的需求是什么，选择性的学习相关的Linux知识，安装Linux的知识先不折腾了，手头上暂时没有相关的机器，也没有精力去折腾，这里直接展示怎么驾驭Linux，下面直接上正文！
## Linux 指令
首先是linux终端，什么是Linux的终端，我刚接触Linux的时候也是云里雾里的，不知所云，Linux终端就是一个窗口（支持输入命令的窗口），如图
![Linux 终端窗口]({{ assets_base_url }}/images/blog/linux.png){: width="auto" height="auto" style="display:block;margin:auto;"}

你可以在Linux的这个终端界面输入各种指令，然后他会返回指令的运行结果。
![Linux 终端窗口命令]({{ assets_base_url }}/images/blog/linuxcommand.png){: width="auto" height="auto" style="display:block;margin:auto;"}

看了上面的图片，应该会对Linux的操作方式有个大概的了解，还是不清楚也没关系，下面开始介绍一些具体操作，有条件的朋友可以拿起键盘跟着敲试试看。

## 文件指令
从文件管理到文件的路径开始操作  
1. 查看当前目录位置
~~~Shell
pwd
~~~
2. 在这个位置新建一个名字为test的文件夹

mkdir test
~~~
3. 进入test文件夹
~~~Shell
cd test
~~~
4. 在test文件夹里新建text.txt文件
~~~Shell
touch text.txt
~~~
5. 打开text.txt文件
6. 在text.txt文件输入12345
7. 保存text.txt文件
8. 关闭text.txt文件
~~~Shell
echo 12345 >>text.txt
~~~
上面三个操作这一个命令就可以完成
9. 打开文件夹，检查test文件夹以及text.txt文件内容
![Linux 演示]({{ assets_base_url }}/images/blog/linux演示.png){: width="auto" height="auto" style="display:block;margin:auto;"}


关于Linux的命令很多，这个不需要去刻意的背诵记忆，常用的指令就那么几个，用多了自然就会了，冷门的指令有个印象，知道有这种命令操作就行了，等要用的时候再网上查一下就可以了。文末附录了两个速查的链接可以点击进去看看
*tips：* 在终端界面，按下*tab键*可以查看所有可用的命令，在命令输入一半的时候，按下Tab键可以*自动补齐命令*，在命令太长或者记忆混乱的时候可以按下此键找点灵感。
## linux 命令速查
- 文件管理
- 文档编辑
- 磁盘管理
- 磁盘维护
- 网络通讯
- 系统管理
- 系统备份
- 备份压缩
- 设备管理
- 其他命令


## 参考链接
[linux中国](https://linux.cn/)  
[linux官方](https://www.linux.org/)  
[linux命令速查](https://www.linuxcool.com/)  
[linux命令速查-菜鸟编程](https://www.runoob.com/linux/linux-command-manual.html)  


