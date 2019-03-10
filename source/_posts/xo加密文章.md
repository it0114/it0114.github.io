title: Hexo加密文章
toc: true
author: Yam
tags:
  - Hexo
  - git
  - 插件
categories:
  - Hexo
date: 2019-02-27 16:01:00
---
# Hexo-Blog-Encrypt
>github文档地址:https://github.com/MikeCoder/hexo-blog-encrypt/blob/master/ReadMe.zh.md

# 安装
在hexo根目录中的package.json中添加`"hexo-blog-encrypt": "1.1.*"`依赖，然后再在hexo根目录中执行`npm install`命令，等待自动安装。

# 使用方法
1. 在根目录中的`_config.yml`启用插件。
```
	# Security
##
encrypt:
    enable: true
    
```

2. 每次编写文章的时候，加上标头，如`password`,`abstract`,`message`.
```
---
title: Hexo加密文章
date: 2019-02-27 16:18:02
tags:
    - 插件
    - Hexo
    - git
    
password: Mike
abstract: Welcome to my blog, enter password to read.
message: Welcome to my blog, enter password to read.
---
```
 - password: 是该博客加密使用的密码
 - abstract: 是该博客的摘要，会显示在博客的列表页
 - message: 这个是博客查看时，密码输入框上面的描述性文字
 

3. 如果不想每篇文章都添加描述，那么就执行一下的代码
```
# Security
##
encrypt:
    enable: true
    default_abstract: 我是文章摘要.</br>
    default_message: 我是密码框上面的文章.

```




