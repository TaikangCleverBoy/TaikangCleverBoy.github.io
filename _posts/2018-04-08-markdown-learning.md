---
layout: post
title: 先从熟练掌握 Markdown 开始
date:   2018-04-08 14:46
description: 学习Markdown常用语法
feature-img: "assets/img/thumbnails/20180408-markdown.jpeg"
thumbnail: "assets/img/thumbnails/20180408-markdown.jpeg"
comments: true
tags: [markdown]
---
    
<!--more-->

* auto-gen TOC:
{:toc}

### 1、标题
标题分成6级，前面使用 # 号标识
>     # 1级标题
>     ## 2级标题
>     ### 3级标题
>     #### 4级标题
>     ##### 5级标题
>     ###### 6级标题 

<br/>
### 2、区块引用
> 段落前面加一个 ">"，可以直接引入一个段落，用于标识重点强调内容，而且应用可以嵌套，可以在区块中加其它的 markdown 语法

<br/>
### 3、列表
> **无序列表**
> * 香蕉
> * 苹果
> * 橘子

> **有序列表**
> 1. 香蕉
> 2. 苹果
> 3. 橘子

<br/>
### 4、代码区块（语法高亮）
**CSS**
```css
#container {
  float: left;
  margin: 0 -240px 0 0;
  width: 100%;
}
```

{% highlight scss linenos %}
.highlight {
  margin: 0;
  padding: 1em;
  font-family: $monospace;
  font-size: $type-size-7;
  line-height: 1.8;
}
{% endhighlight %}

**JS**
{% highlight js %}
// count to ten
for (var i = 1; i <= 10; i++) {
    console.log(i);
}

// count to twenty
var j = 0;
while (j < 20) {
    j++;
    console.log(j);
}
{% endhighlight %}

**HTML**
```html
{% raw %}<nav class="pagination" role="navigation">
  {% if page.previous %}
    <a href="{{ site.url }}{{ page.previous.url }}" class="btn" title="{{ page.previous.title }}">Previous article</a>
  {% endif %}
  {% if page.next %}
    <a href="{{ site.url }}{{ page.next.url }}" class="btn" title="{{ page.next.title }}">Next article</a>
  {% endif %}
</nav><!-- /.pagination -->{% endraw %}
```

**Ruby**
```ruby
module Jekyll
  class TagIndex < Page
    def initialize(site, base, dir, tag)
      @site = site
      @base = base
      @dir = dir
      @name = 'index.html'
      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag_index.html')
      self.data['tag'] = tag
      tag_title_prefix = site.config['tag_title_prefix'] || 'Tagged: '
      tag_title_suffix = site.config['tag_title_suffix'] || '&#8211;'
      self.data['title'] = "#{tag_title_prefix}#{tag}"
      self.data['description'] = "An archive of posts tagged #{tag}."
    end
  end
end
```

**Java**
```java
/**
 * @description: 最大回文串: 中心扩散算法
 */
public class SpreadFromCenter {
    public String longestPalindrome(String s)
    {
        for (int i=0; i<s.length(); i++)
        {
            // 奇数回文串
            calculate(s, i, 0);
    
            // 偶数回文串
            calculate(s, i, 1);
        }
        return longest;
    }
    
    public void calculate(String s, int idx, int offset)
    {
        int left = idx;
        int right = idx + offset;
        int length = s.length();
    
        while (left>=0 && right<length && s.charAt(left) == s.charAt(right))
        {
            left --;
            right ++;
        }
    
        String currentLongest = s.substring(left + 1, right);
    
        if (currentLongest.length() > longest.length())
        {
            longest = currentLongest;
        }
    }
}
```

**列表中的代码块**
> 1. 香蕉
> 2. 苹果
    ```ruby
       def print_hi(name)
         puts "Hi, #{name}"
       end
       print_hi('Tom')
       #=> prints 'Hi, Tom' to STDOUT.
    ```
>  3. 橘子

**外部脚本直接嵌入**
<script src="https://gist.github.com/mmistakes/77c68fbb07731a456805a7b473f47841.js"></script>

**行内代码**
<br/>Java 语言第一课: `System.out.println("Hello World!");` .

<br/>
### 5、分隔线
* * *
***
*****
- - -
---

<br/>
### 6、超链接（行内式、参考式）

> **行内式：方括号 + 小括号**
    <br/>我是 [百度](http://www.baidu.com/ "百度")
    <br/>[京东](http://www.jd.com/) 是我


> **参考式：两个方括号**
    <br/>我是 [百度] [1].

[1]: <http://www.baidu.com> "百度是全球最大的中文搜索引擎提供商"

<br/>
### 7、强调加粗，倾斜

>  **强调**

<br/>
### 8、图片引入

![Lin Zhi Lin]({{ site.baseurl }}/assets/img/content/20180408/linzhilin.jpeg)

![Image of a glass on a book]({{ site.baseurl }}/assets/img/pexels/book-glass.jpeg)

<br/>
### 9、表格

水果          | 蔬菜
------------- | -------------
苹果          | 西红柿
鸭梨          | 土豆

First Header  | Second Header  | Third Header
:-------------| :------------: | ------------:
Content Cell  | Content Cell   | Content Cell
Content Cell  | Content Cell   | Content Cell

<br/>
### 10、数学公式（KaTeX）

行内公式：$$S_n = a \times \frac{1-r^n}{1-r}$$

单独一行公式：

$$ f(x) = \int \frac{2x^2+4x+6}{x-2} $$

<br/>
### 11、注意事项（KaTeX）
* feature 图片是正文大图片，thumbnail 是外部小图片
* 换行标签最好放到标题上面，防止跟其它标签混在一起，无法完成换行
* 强调是两个 * 号，注意中间没有空格
* 表格上下都要换行
* 表格可以通过在小短杠左右加冒号决定对齐方式
* 如果用 markdown 实在无法表示所需样式，可以直接使用 HTML + CSS

<br/>
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