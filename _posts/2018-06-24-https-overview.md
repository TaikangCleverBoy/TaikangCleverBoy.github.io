---
layout: post
title: Https全流程梳理
date:   2018-06-24 23:00
description: 粗线条总结 https 所需了解的技术环节
feature-img: "assets/img/content/20180624/https.jpeg"
thumbnail: "assets/img/thumbnails/20180624-https.jpeg"
comments: true
tags: [https]
---

<!--more-->

<p><font size="6" face="黑体"><strong>目录</strong></font></p>
* auto-gen TOC:
{:toc}

<br/>
### 1、HTTPS 概念
HTTPS 本质上也是使用 HTTP 协议传输数据，只是在之前的 TCP 层上面增加了一层安全的 SSL 层，对所有的数据都加密进行传输，客户端和服务端按照约定好的 "会话秘钥" 加解密数据。
HTTPS 的网络分层情况如下图所示。
    
![网络分层]({{ site.baseurl }}/assets/img/content/20180624/https-网络分层.png)

    

<br/>
### 2、HTTPS 基本原理

<br/>
### 3、实现 HTTPS 涉及相关技术

<br/>
<aside class="related">
  <h2>相关文章</h2>
  <ul class="related-posts">
    <li>
      <a href="https://zh.wikipedia.org/wiki/%E5%82%B3%E8%BC%B8%E5%B1%A4%E5%AE%89%E5%85%A8%E6%80%A7%E5%8D%94%E5%AE%9A ">
        维基百科 SSL
      </a>
    </li>
    <li>
        <a href="http://www.ruanyifeng.com/blog/2014/02/ssl_tls.html ">
          阮一峰，SSL
        </a>
    </li>
    <li>
        <a href="https://www.linuxidc.com/Linux/2016-05/131147.htm">
          SSL/TLS概览
        </a>
    </li>
    <li>
        <a href="https://www.jianshu.com/p/b0b6b88fe9fe">
          1- Https流程和原理
        </a>
    </li>
    <li>
        <a href="http://www.chinaz.com/web/2017/0105/639110.shtml">
          在阿里云申请 Symantec免费SSL证书操作流程
        </a>
    </li>
    <li>
        <a href="http://www.ruanyifeng.com/blog/2013/06/rsa_algorithm_part_one.html">
          阮一峰 RSA算法原理（一）
        </a>
    </li>
    <li>
        <a href="https://aotu.io/notes/2016/08/16/nginx-https/index.html">
          Nginx 配置 Https 服务器
        </a>
    </li>
    <li>
        <a href="https://www.cnblogs.com/guogangj/p/4118605.html">
          蒋国纲 《那些证书相关的玩意儿(SSL,X.509,PEM,DER,CRT,CER,KEY,CSR,P12等)》
        </a>
    </li>
  </ul>
</aside>