---
layout: post
title:  "LDAP Search with Simple authentication"
description: "如何指定使用LDAP simple authentication"
categories: [programming, LDAP]
disqus_comments: true
date: 2014-02-14 20:22:00 UTC
---

部署了Apache DS之后尝试在cygwin下用命令行来直接查询

```sh
$ ldapsearch -h localhost -port 10389 -b "o=supernova" -s sub "(cn=Scott Wu)"
```

得到以下纠结提示

```sh
SASL/DIGEST-MD5 authentication started
Please enter your password:
Please enter your realm:
```

好吧，其实我只是做个简单测试，直接用simple认证就好，干嘛搞那么复杂。
打开configuration页面，默认每种认证方式都选上了，先去掉其他，只保留simple，然后勾选上“Allow Anonymous Access". 保存退出重启Apache DS。
这次提示

```sh
ldap_sasl_interactive_bind_s: Unknown authentication method (-6)
```
看来还是默认查找SASL认证，理论上应该可以由客户端选择认证方式吧。研究一下ldap的man，果然如此。

```sh
Common Options:
 -x		Simple authentication
 -w passwd 	bind password
 -W 		prompt for bind password
 -y 		Read password from file.
```

问题顺利解决