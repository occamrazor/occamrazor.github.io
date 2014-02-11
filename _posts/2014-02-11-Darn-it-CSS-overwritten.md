---
layout: post
title:  "Darn it: CSS overwritten"
description: "After posting my first blog into github, I feel it is boring to show a monotonous web page. I want to get more 'fashion' style. Relate to style, CSS 3 is first thing in my mind, and then I got a tricky issue in next several hours."
categories: [tools, programming, HTML5, CSS3]
disqus_comments: true
date: 2014-02-10 23:22:00 UTC

---

After posting my first blog into github, I feel it is boring to show a monotonous web page. I want to get more 'fashion' style. Relate to style, CSS 3 is first thing in my mind, and then I got a tricky issue in next several hours.
The first thing is to google what can be reused. Luckly there is a good template which catch my eyeball immediately. The only thing I need to change is to apply prettify plugin because I need to past some source codes in my blog.

Prettify is an amazing plugin which can adapt to almost all languages in world. You can get it from <a href="https://code.google.com/p/google-code-prettify/">Google-Code-Prettify</a>.

Everything is fine except my code example is always overflow, so a scroll bar will be shown on the page. I hate it. Obviously it can be solved by changing style. Go to prettify css directly! Luckly you can find pre element. What you need to do is adding

```css
  word-wrap: break-word; word-break:break-all;
```
Unfortunately nothing is changed. It almost changed my mind about CSS. Finally I have to debug the page via Chrome (Never forget F12). Finally I was shocked: a customize CSS is hidden in a special folder which overwrite pre. After changing it, everything is fine.

Finally there is only one word in my mind: Egg-pain!


