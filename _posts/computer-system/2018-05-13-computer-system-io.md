---
layout: post
title: 深入理解计算机系统-系统级I/O
date:   2018-05-08 14:46
description: 了解系统级I/O常见概念
feature-img: "assets/img/thumbnails/20180408-markdown.jpeg"
thumbnail: "assets/img/thumbnails/20180408-markdown.jpeg"
comments: true
tags: [computer-system]
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
    * 打开文件（open）: 内核返回文件描述符
    * 标准文件： 标准输入（0）、标准输出（1）、标准错误（2）
    * 改变文件当前位置 k
    * 读写文件（read/write）
    * 关闭文件（close）

```c
// 打开文件
int open(char *filename, int flags, mode_t mode);

// 读文件 n 个字节到 buf
ssize_t read(int fd, void *buf, size_t n);

// 写 buf 的 n 个字节到文件
ssize_t write(int fd, const void *buf, size_t n);
```
    
3. 文件分类
    * 普通文件：包含文本文件和二进制文件，文本文件存放 ASCII 或 Unicode 字符
    * 目录：包含一组 link，每个 link 将一个文件名映射到一个文件，这个文件还可能是另外一个目录，每个目录下至少含有两个条目，
”.“ 是到该目录自身的链接， ".." 是到目录层次结构中父目录的链接
    * 套接字：与另外一个进程进行跨网络通信的文件
    
4. Linux 内核目录层次结构
    Linux 内核将所有文件都组织成一个目录层次结构，由名为 /（斜杠） 的根目录确定，系统中的每个文件都是根目录的直接或间接的后代，
那么我们常见的一些目录分别代表什么含义，存放什么文件呢？ 这里我们给出一个简介。
    * bin：
    * boot：
    * dev：
    * etc：
    * home：
    * lib：
    * usr：
    * opt：
    * proc：

5. 文件路径名
    * 绝对路径名：以一个斜杠开始，表示从根节点开始的路径
    * 相对路径名：以文件名开始，表示从当前工作目录开始的路径
    
6. ssize_t 与 size_t 区别
    ssize_t：有符号 long
    size_t：无符号 long
    
7. RIO（Robust I/O 健壮的 I/O 包）
    * 无缓冲的输入输出函数
    * 带缓冲的输入输出函数
    
```c
// rio 读文件
ssize_t rio_readn(int fd, void *usrbuf, size_t n);

// rio 写文件
ssize_t rio_writen(int fd, void *usrbuf, size_t n);

// 读文件，从内部读缓冲区复制一行文本行，当缓冲区变空时，会自动调用 read 重新填满缓冲区
ssize_t rio_readlineb(rio_t *rp, void *usrbuf, size_t maxlen);

// 读文件，文件既包含文本行，也包含二进制数据的时候使用
ssize_t rio_readnb(rio_t *rp, void *usrbuf, size_t n);
```
    
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