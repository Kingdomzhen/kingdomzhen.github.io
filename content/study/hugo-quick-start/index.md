+++
title = "Hugo 博客搭建全指南"
date = "2026-03-10"
description = "从零开始，一步一步搭建你的 Hugo 个人博客"
tags = ["Hugo", "教程", "博客"]
categories = ["技术"]
+++

## 前言

Hugo 是目前最快的静态网站生成器，用 Go 语言编写，构建速度在**毫秒级别**。这篇指南带你从零搭建一个博客。

## 安装 Hugo

### Windows

```powershell
winget install Hugo.Hugo.Extended
```

### macOS

```bash
brew install hugo
```

### Linux

```bash
sudo apt install hugo
```

## 创建站点

```bash
hugo new site my-blog
cd my-blog
```

## 添加主题

以 PaperMod 为例：

```bash
git init
git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
```

然后在 `hugo.toml` 中配置：

```toml
theme = "PaperMod"
```

## 写文章

```bash
hugo new post/my-article/index.md
```

## 本地预览

```bash
hugo server -D
```

打开 `http://localhost:1313` 即可看到效果。

## 部署到 GitHub Pages

1. 在 GitHub 创建仓库 `username.github.io`
2. 构建站点：`hugo --minify`
3. 将 `public/` 推送到 GitHub

## 小结

Hugo 的优势在于：
- 构建速度快
- 单二进制，无依赖
- 模板灵活
- 社区主题丰富

现在就开始你的博客之旅吧！
