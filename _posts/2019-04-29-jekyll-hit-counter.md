---
layout: post
title: Jekyll 访问统计
categories: [Tech]
---

这几天下班都在折腾Jekyll, 想给每篇文章添加一个访问统计，看看大家更喜好那类文章。
看了很多相关的工具，无意中发现了 [Hit Kounter](https://jerryzou.com/posts/introduction-to-hit-kounter-lc/) 这个工具.
简单、完美适配Jekyll, 主要是不用担心因为添加了Google统计就导致网站访问不了.

使用方法非常简单：

1. 首先在HTML head中加入下面代码:

```html
<script src="https://cdn1.lncld.net/static/js/av-min-1.5.0.js"></script>
<script src="https://jerry-cdn.b0.upaiyun.com/hit-kounter/hit-kounter-lc-0.3.0.js"></script>
```

2. 如果想在文章页面中显示统计，在文章模板文件中添加代码：

```html
浏览<span data-hk-page="current"> - </span>次
```

3. 如果想引用别的链接的统计，比如在首页显示各页面的访问次数，可以在首页模板中添加代码：

```html
浏览 <span data-hk-page="https:{{ post.url | prepend: site.url }}">
```

post.url 是引用文章的链接，prepend: site.url 的意思是添加域名前缀，https: 也必须加，要不是 Hit Kounter 无法正常工作。

That's all, git push 以后就可以看到各文章的访问流量了。