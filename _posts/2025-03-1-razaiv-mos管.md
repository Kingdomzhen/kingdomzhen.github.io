---
layout: post
title: mos 管的一些特性
categories: [analog, razaiv]
description: 博客
keywords: analog, razaiv
mathjax: true
---
挖坑ing  
mos管的器件介绍
测试

**目录**

* TOC
{:toc}

---


## 前言
mos管是最基本的器件，玩转模拟IC离不开mos管，在这一篇文章介绍mos管的小信号模型以及常见参数。

## 初识mos管
mos管分为Nmos和Pmos，在芯片设计领域，所有的这些mos管都是蚀刻在一块硅基底上。这些相关的详细知识在半导体物理里面会有介绍。理解mos管的工作特性也需要了解一下mos管的半导体结构。这里暂时默认大家都对mos管有一定的了解再看到这篇文章。

## mos管小信号模型
<div align="center"><img width="auto" height="auto" src="{{ assets_base_url }}/images/blog/2025-3-9-mos.png"/>
<p>拉扎维书中的小信号模型图</p>
</div>
如图，认识mos管的小信号模型，对电路的分析很有必要！  
图中介绍了几种常见的mos管的等效小信号模型，比较常用的是c模型，d模型适合在考虑二级效应以及更精确的分析中应用。

### 电流计算公式
Id，代表流过漏极的电流，这个电流和mos管的三端有如下关系
不考沟道长度调制效应

$$


$$

考虑沟道长度调制效应
$$


$$

### 跨导
gm-mos管电压转换电流的能力  
$$
\begin{aligned}\mathrm{gm}&=\frac{\partial I_{\mathrm{D}}}{\partial V_{\mathrm{GS}}}|_{V_{\mathrm{ISS},\mathrm{cons}}}\\&=\mu_{n}C_{ox}\frac{W}{L}\left(V_{GS}-V_{TH}\right)\end{aligned}\
$$

考虑体效应后  

$$
\begin{equation}\begin{aligned}\mathrm{gm}&=\mu_{\mathrm{n}}C_{\mathrm{ox}}\frac{W}{L}(\left(V_{\mathrm{GS}}-V_{\mathrm{TH}}\right)(1+\lambda V_{DS})\\&=\sqrt{2\mu_{\mathrm{n}}C_{OX}(W/L)I_{\mathrm{D}}\left(1+\lambda V_{\mathrm{ns}}\right)}\\&=\frac{2I_{\mathrm{D}}}{V_{\mathrm{GS}}-V_{\mathrm{TH}}}\end{aligned}\end{equation}
$$

### 输出电阻
ro，输出电阻表示源漏之间的等效电阻  

$$
\begin{aligned}\mathrm{ro}&=\frac{\partial V_{DS}}{\partial I_{D}}\\&=\frac{1}{\partial I_{\mathrm{D}}/\partial V_{\mathrm{DS}}}\\&=\frac{1}{\frac{1}{2}\mu_{\mathrm{n}}C_{\mathrm{ox}}\frac{W}{L}(V_{\mathrm{GS}}-V_{\mathrm{TH}})^{2}\lambda}\\&\approx\frac{1+\lambda V_{DS}}{\lambda I_{D}}\\&\approx\frac{1}{\lambda I_{D}}\end{aligned}
$$

## mos 管的工作区

### 截至区

### 三极管区



## mos管的二级效应

### 体效应（body effect）

### 沟道调制效应

### 亚阈值效应




## 参考资料
[mos管结构](https://zhuanlan.zhihu.com/p/163702360)  