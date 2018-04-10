---
layout: post
title: 先从熟练掌握 Markdown 开始
date:   2018-04-08 14:46
description: 学习Markdown常用语法
comments: true
tags: [markdown]
---
    
学习掌握 Markdown <br/>
http://itmyhome.com/markdown/article/about/readme.html <br/>
https://segmentfault.com/a/1190000004543870
<!--more-->

### 标题
标题分成6级，前面使用 # 号标识

# 1级标题
## 2级标题
### 3级标题
#### 4级标题
##### 5级标题
###### 6级标题 


### 区块引用
> 段落前面加一个 ">"，可以直接引入一个段落，用于标识重点强调内容，而且应用可以嵌套，可以在区块中加其它的 markdown 语法
>> 我是嵌套的区块引用


### 列表
##### 无序列表
* 香蕉
* 苹果
* 橘子

##### 有序列表
1. 香蕉
2. 苹果
3. 橘子


### 代码区块（语法高亮）
##### CSS: 带行号, 不带行号

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

##### HTML
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

##### Ruby
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

##### 列表中的代码块
1. 香蕉
2. 苹果

   ```ruby
   def print_hi(name)
     puts "Hi, #{name}"
   end
   print_hi('Tom')
   #=> prints 'Hi, Tom' to STDOUT.
   ```
        
3. 橘子

##### 外部脚本直接嵌入
<script src="https://gist.github.com/mmistakes/77c68fbb07731a456805a7b473f47841.js"></script>
 

<br/><br/>
<aside class="related">
  <h2>相关文章</h2>
  <ul class="related-posts">
    <li>
        <a href="http://kresnikwang.github.io///journey/2015/06/05/kresnik.co-%E5%8D%9A%E5%AE%A2%E6%90%AC%E5%AE%B6%E5%91%8A%E7%A4%BA.html">
          kresnik.co博客搬家告示
          &nbsp;&nbsp;<small><time datetime="2015-06-05T00:00:00+00:00">05 Jun 2015</time></small>
        </a>
    </li>
  </ul>
</aside>