---
layout: post
title:  "Git: How to set multiple accounts for different git repository"
description: "I have a github account for my personal projects and blogs. Meanwhile my company is also using git, but I just have one laptop. I shall be able to access both of them from my laptop automatically. No account switch, no boring system configuration"
categories: [tools, programming, git, ssh]
disqus_comments: true
date: 2014-02-13 20:22:00 UTC

---

<em>Question</em>

I have a github account for my personal projects and blogs. Meanwhile my company is also using git, but I just have one laptop. I shall be able to access both of them from my laptop.

<em>Solution</em>

Solution is always simple and cheap. I am using cygwin as default shell. Please use it as a reference if you are using windows.

<h1>Step 1: Generate different key files</h1>

Obviously different git sites need to have solely key file.

```sh
$ ssh-keygen -t rsa -C "scopic78@hotmail.com" -f id_rsa_git_hub
$ ssh-keygen -t rsa -C "scott.wu@mycompany.com" -f id_rsa_company
```

Now you will get 4 files: id_rsa_git_hub, id_rsa_git_hub.pub, id_rsa_company, id_rsa_company.pub

<h1>Step 2: Register your pub key </h1>

You need to register pub keys into github and private git server, such as gerrit.
No tips. You shall know how to do it.

<h1>Step 3: ssh configuration</h1>

This is most important step. You need to create a file named "config" in your ~/.ssh folder. The content :

```sh
##Github
Host github
HostName github.com
User git
IdentityFile ~/.ssh/id_rsa_git_hub
##private gerrit
Host gerritforge.mycompany.com
User git
IdentityFile ~/.ssh/id_rsa_company
```

Now everything is done. You can clone repos from different platform.

<h1>Step 4: Git configuration</h1>

As you known Git is using your user.name and user.email to show author in project. Please don't forget to configure your git. Later I will write something about this basic git configuration.

