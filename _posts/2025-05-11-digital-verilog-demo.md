---
layout: post
title: Verilog 实例demo
categories: [digital, Verilog，code]
description: 博客
keywords: digital, Verilog
---
用一个简单的例子来介绍verilog的用法



**目录**

* TOC
{:toc}

---


## verilog概述
Verilog能够在多种抽象级别对数字逻辑系统进行描述，Verilog的设计初衷是成为一种基本语法与C语言相近的硬件描述语言。当前广泛使用的硬件描述语言包括VHDL以及Verilog HDL（VHSIC Hardware Description Language）；同时verilog还衍生出了一些变种语言如System Verilog、Verilog-AMS等等，丰富了Verilog语言的应用场景。  

<div align="center"><img width="auto" height="auto" src="{{ assets_base_url }}/images/blog/2025-5-12-verilog介绍.png"/>
<p>不同语言在芯片设计上的主流场景</p>
</div> 

verilog语言和VHDL语言功能基本相同，在目前的项目上可以支持混用，但是VHDL的语法上更加严格一些，verilog语言更倾向于C语言，如果是入门学习，作者个人认为学习verilog语言就足够了，学完了Verilog语言基本就能看懂VHDL程序的意思。

## 实例
话不多说，先看看verilog程序整什么样：
Verilog程序一般分为程序和测试程序（一般习惯叫Testbench），测试程序会依据程序的功能尽可能的覆盖多的场景。

### verilog程序实例

~~~Verilog
// and2x模块：实现两个输入信号的与逻辑
module and2x(
    input a,  // 输入信号a
    input b,  // 输入信号b
    output r  // 输出信号r，等于a和b的与逻辑结果
);
    // 由于a和b已经定义为input，这里不需要再次定义wire
    // wire a, b, r; 这行代码是多余的，应该删除

    // assign语句将a和b的与逻辑结果赋值给输出r
    assign r = a & b;
endmodule
~~~


### verilog testbench程序实例
再看看verilog程序的测试程序长什么样子
~~~Verilog
`timescale 1ns / 1ps

module tb_and2x;

  // 定义信号
  reg a;
  reg b;
  wire r;

  // 实例化 and2x 模块
  and2x uut (
    .a(a),
    .b(b),
    .r(r)
  );

  // 测试过程
  initial begin
    // 初始化输入
    a = 0;
    b = 0;
    #10; // 等待 10ns

    // 测试第一个条件
    a = 1;
    b = 0;
    #10; // 等待 10ns

    // 测试第二个条件
    a = 0;
    b = 1;
    #10; // 等待 10ns

    // 测试第三个条件
    a = 1;
    b = 1;
    #10; // 等待 10ns

    // 测试结束
    $finish;
  end

  // 监控输出
//end    
  initial begin
    $dumpfile("out.vcd");
    // This will dump all signal, which may not be useful
    //$dumpvars;
    // dumping only this module
    //$dumpvars(1, testbench);
    // dumping only these variable
    // the first number (level) is actually useless
    $dumpvars(0, testbench);
end  

endmodule
~~~


## verilog的使用场景



## 参考资料
[verilog语言同类](https://blog.csdn.net/u011729865/article/details/119376935)  
[verilog和VHDL的区别](https://www.cnblogs.com/Colin-Cai/p/8547099.html)  