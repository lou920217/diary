---
layout: post
title: 从输入网址到页面呈现都发生了什么
category: interview
tags: [browser]
---
今天来分析下“从输入网址到页面呈现都发生了什么”这道经典面试题，因为这道题设计知识面极广，可以很好的考察一个前端工程师的技术栈广度及深度，所以在面试中会不可避免的遇到，在此先一步总结下！

从输入网址到页面呈现这个过程大致可以分为以下这几个部分：

1. 网络通信
2. 浏览器渲染页面

浏览器渲染页面分为：
1. 解析HTML
2. 构建DOM树
3. DOM树与样式树附着构建渲染树
4. 布局
5. 绘制

解析HTML：
1. 解析器剖析（HTML解析器、CSS解析器，JS解析器）
2. 资源加载剖析（css外部文件，js外部文件，js执行，HTML图片资源，css图片资源，css font资源等的加载顺序）
