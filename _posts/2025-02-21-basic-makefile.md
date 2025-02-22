---
layout: post
title: makefike 笔记
categories: [makefike, basic,Linux]
description: makefike 编辑器教程
keywords: makefike, basic,Linux
---
makefike 学习笔记

makefike可以把一大串Linux 指令封装成独立的命令执行，在需要处理复杂任务时，可以把命令编辑到makefile文件里，然后简单的命令就可以执行复杂的操作了，化繁为简，大大提高code效率。

![makefile 文件](https://raw.githubusercontent.com/Kingdomzhen/blog-photo/main/photo/makefile.png){: width="400" height="192" style="display:block;margin:auto;"}

## makefile 使用方法
makefile在linux中直接以makefile形式存在，在使用时，直接在终端输入命令  
~~~
make <command>
~~~
例如：下面是一段markdowm文件的源代码
~~~
test:
        @echo "hello test"
~~~
要执行这个makefile的需要在终端下的操作如下：
~~~
[user]$ make test
~~~
输入这段命令后，终端会打印出`hello test`字样，此时的终端将会变成
~~~
[user]$ make test
hello test
~~~
这就是makefile文件的使用方法，接下来介绍一下makefile文件格式

## makefile 文件格式
Makefile基本格式如下:
~~~
target ... : prerequisites ...
    command
    ...
    ...
~~~
其中,

target        - 目标文件, 可以是 Object File, 也可以是可执行文件  
prerequisites - 生成 target 所需要的文件或者目标  
command       - make需要执行的命令 (任意的shell命令), Makefile中的命令必须以 [tab] 开头  
 

显示规则 :: 说明如何生成一个或多个目标文件(包括 生成的文件, 文件的依赖文件, 生成的命令)  
隐晦规则 :: make的自动推导功能所执行的规则  
变量定义 :: Makefile中定义的变量  
文件指示 :: Makefile中引用其他Makefile; 指定Makefile中有效部分; 定义一个多行命令  
注释     :: Makefile只有行注释 "#", 如果要使用或者输出"#"字符, 需要进行转义, "\#"  

## makefile 经典实例
~~~
objects = main.o kbd.o command.o display.o \
		insert.o search.o files.o utils.o

edit : $(objects)
	cc -o edit $(objects)
main.o : main.c defs.h
	cc -c main.c
kbd.o : kbd.c defs.h command.h
	cc -c kbd.c
command.o : command.c defs.h command.h
	cc -c command.c
display.o : display.c defs.h buffer.h
	cc -c display.c
insert.o : insert.c defs.h buffer.h
	cc -c insert.c
search.o : search.c defs.h buffer.h
	cc -c search.c
files.o : files.c defs.h buffer.h command.h
	cc -c files.c
utils.o : utils.c defs.h
	cc -c utils.c
clean :
	rm edit $(objects)
~~~
在这个例子里，我们可以知道，maefile可以添加外部文件，一个makefile文件里可以添加多个不同的命令



## 参考链接
[GNU make](https://liaoxuefeng.com/books/makefile/makefile-basic/)  
[WittXie的makefile教程](https://www.cnblogs.com/wittxie/p/9836097.html)  
[博客园的makefile教程](https://www.cnblogs.com/wang_yb/p/3990952.html)  
[廖雪峰的makefile教程](https://liaoxuefeng.com/books/makefile/makefile-basic/)  


