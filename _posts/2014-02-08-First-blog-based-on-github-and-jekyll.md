---
layout: post
title:  "第一份基于Github+Jekyll的Blog"
description: "经过几个小时的摸索终于开始搭建基于github page的blog。之前在wordpress等地也安家过，一方面wordpress的几次改版搞得身心疲惫，同时自己也未能坚持，反而通过evernote倒是有一些日常积累。在不用翻墙的今天，痛定思痛，正儿八经的给自己找个安家之处。总得说来在windows上搭建这个平台实属不易，尤其是作为一个伪Linux爱好者，还是通过cygwin做了一层封转，不过磕磕碰碰总算整出来了。"
categories: [tools, programming]
disqus_comments: true
date: 2014-02-08 18:48:00 UTC

---

经过几个小时的摸索终于开始搭建基于github page的blog。之前在wordpress等地也安家过，一方面wordpress的几次改版搞得身心疲惫，同时自己也未能坚持，反而通过evernote倒是有一些日常积累。在不用翻墙的今天，痛定思痛，正儿八经的给自己找个安家之处。

总得说来在windows上搭建这个平台实属不易，尤其是作为一个伪Linux爱好者，还是通过cygwin做了一层封转，不过磕磕碰碰总算整出来了。

一个折腾了半天的问题。 启动Jekyll serve是提示

```sh
 Liquid Exception: No such file or directory - C:\Windows\system32\cmd.exe in _posts/2014-02-04-welcome-to-jekyll.markdown
```

在github上找到办法异常简单：

```sh
export COMSPEC=C:\Windows\system32\cmd.exe
```

将此变量设置到~/.bashrc中就OK了！
