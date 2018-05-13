---
layout: post
title: 深入Java并发包（一）
date:   2018-05-08 14:46
description: 总结回顾Java并发包
feature-img: "assets/img/thumbnails/20180408-markdown.jpeg"
thumbnail: "assets/img/thumbnails/20180408-markdown.jpeg"
comments: true
tags: [markdown]
---

<!--more-->

<p><font size="6" face="黑体"><strong>目录</strong></font></p>
* auto-gen TOC:
{:toc}

<br/>
### 1、UNIX I/O
1. 概念
    一个 Linux 文件就是一个 m 个字节的序列：
       $$B_0$$, $$B_1$$, ..., $$B_k$$, ..., B$$B_m-1$$
所有的 I/O 设备（网络、磁盘、终端）都是文件，所有的输入输出都被当做对相应文件的读和写来执行。这种将设备映射为文件的方式，允许 Linux 内核引出一
个简单、低级的应用接口，称为 Unix I/O，使得所有的输入和输出都能以一种统一且一致的方式来执行。
 
2. 标准接口
    * 打开文件: 内核返回文件描述符
    * 标准文件： 标准输入（0）、标准输出（1）、标准错误（2）
    * 改变文件当前位置 k
    * 读写文件
    * 关闭文件
    
3. 文件分类
    * 普通文件：包含文本文件和二进制文件，文本文件存放 ASCII 或 Unicode 字符
    * 目录：包含一组 link，每个 link 将一个文件名映射到一个文件，这个文件还可能是另外一个目录
    * 套接字：与另外一个进程进行跨网络通信的文件



<aside class="related">
  <h2>相关文章</h2>
  <ul class="related-posts">
    <li>
        <a href="https://github.com/riku/Markdown-Syntax-CN/blob/master/syntax.md#%E6%A0%87%E9%A2%98">
          Markdown 语法说明 (简体中文版)
          &nbsp;&nbsp;<small><time datetime="2018-04-10T00:00:00+00:00">10 April 2018</time></small>
        </a>
    </li>
  </ul>
</aside>