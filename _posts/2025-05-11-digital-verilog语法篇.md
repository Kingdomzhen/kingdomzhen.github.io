---
layout: post
title: Verilog 语法篇
categories: [digital, Verilog，code]
description: 博客
keywords: digital, Verilog
---
verilog语法的基本认识


**目录**

* TOC
{:toc}

---

## 前言
verilog的语法入门篇

## 数据类型

- **reg（寄存器）：**  
用于存储逻辑电路中的状态变量，可以通过赋值操作进行更新。其用法类似于其他编程语言中的变量，但不同的是，在 Verilog 中，reg类型的变量可以不仅可以存储数字和布尔值，还可以存储多位二进制数（也可以存储 ASCII 字符）。

- **integer（整数）：**  
用于存储整数类型的变量，可以进行加减乘除等基本算术运算。其范围为 -2^31 到 2^31 - 1。

- **real（实数）：**  
用于存储浮点数类型的变量，可以进行基本的算术运算和一些特殊的数学函数运算。其精度和范围可能因实现而异。

- **time（时间）：**  
用于存储时间类型的变量，可以表示电路中的时间间隔，通常以纳秒为单位。在仿真过程中，时间变量可以用于控制模拟过程的进行。

- **event（事件）：**  
用于在电路中表示事件，可以通过事件触发器（Event Trigger）来控制模块的行为。

- **parameter（参数）：**  
用于在模块内部定义常量，其值在模块实例化时被确定。在模块中，参数可以用于配置模块的行为。

除了上述的变量类型之外，Verilog 中还有其他一些变量类型，如bit、byte、logic等，它们的具体用法和特点可能略有不同。在实际设计中，可以根据需要选择和使用适当的变量类型来实现设计。

## 数值表示
verilog是面向数字电路的编程语言，数值的表示更侧重于二进制的方式，和C语言会有一些区别。
### 数据种类
Verilog HDL 有下列四种基本的值来表示硬件电路中的电平逻辑：

0：逻辑 0 或 "假"  
1：逻辑 1 或 "真"  
x 或 X：未知  
z 或 Z：高阻  
* x 意味着信号数值的不确定，即在实际电路里，信号可能为 1，也可能为 0。  
* z 意味着信号处于高阻状态，常见于信号（input, reg）没有驱动时的逻辑结果。例如一个 pad 的 input 呈现高阻状态时，其逻辑值和上下拉的状态有关系。上拉则逻辑值为 1，下拉则为 0 。  

## 运算符

## 过程控制


## 时序控制
Verilog 提供了 2 大类时序控制方法：时延控制和事件控制。事件控制主要分为边沿触发事件控制与电平敏感事件控制
### 延时控制
延时分为常规延时和内嵌延时
* 常规时延：遇到延迟语句后先延迟一定的时间，然后将当前操作数赋值给目标信号，并没有"惯性延迟"的特点，不会漏掉相对较窄的脉冲。
* 内嵌时延：遇到延迟语句后，先计算出表达式右端的结果，然后再延迟一定的时间，赋值给目标信号。

常规时延

遇到常规延时时，该语句需要等待一定时间，然后将计算结果赋值给目标信号。

格式为：#delay procedural_statement，例如：

~~~
reg  value_test ;
reg  value_general ;
#10  value_general    = value_test ;
~~~

该时延方式的另一种写法是直接将井号 # 独立成一个时延执行语句，例如：

~~~
#10 ;
value_ single         = value_test ;
~~~

内嵌时延

遇到内嵌延时时，该语句先将计算结果保存，然后等待一定的时间后赋值给目标信号。

内嵌时延控制加在赋值号之后。例如：

reg  value_test ;
reg  value_embed ;
value_embed        = #10 value_test ;

### 事件控制
在 Verilog 中，事件是指某一个 reg 或 wire 型变量发生了值的变化后执行的事件。
可以指定上升沿、下降沿、指定信号边沿、多信号边沿等触发方式。

~~~
//信号clk只要发生变化，就执行q<=d，双边沿D触发器模型
always @(clk) q <= d ;                
//在信号clk上升沿时刻，执行q<=d，正边沿D触发器模型
always @(posedge clk) q <= d ;  
//在信号clk下降沿时刻，执行q<=d，负边沿D触发器模型
always @(negedge clk) q <= d ; 
//立刻计算d的值，并在clk上升沿时刻赋值给q，不推荐这种写法
q = @(posedge clk) d ;

//在上升沿和下降沿都触发的，用or或者，连接
//带有低有效复位端的D触发器模型
always @(posedge clk or negedge rstn)    begin      
//always @(posedge clk , negedge rstn)    begin      
//也可以使用逗号陈列多个事件触发

//对所有的输入都敏感
always @(*) begin
//always @(a, b, c, d, e, f, g, h, i, j, k, l, m) begin
//两种写法等价
~~~

## 函数
verilog语言也可以想C语言一样将一段功能的代码封装成函数的形式，在主程序种调用即可，减少主程序代码的繁杂，可以把精力更多的放在写程序的逻辑上面去。


## 任务
将一段代码块封装成一个task，和函数的功能类似，更多的是应用于verilog 测试的代码里面（testbench）。


## 参考连接
[菜鸟语法](https://www.runoob.com/w3cnote/verilog-tutorial.html)  
[博客教程](https://www.cnblogs.com/mikewolf2002/p/10183032.html)  
[中原大學電機系Verilog HDL](https://hom-wang.gitbooks.io/verilog-hdl/content/Chapter_01.html)  
[中原大學電機系Verilog HDL](https://hom-wang.gitbooks.io/verilog-hdl/content/Chapter_01.html)  