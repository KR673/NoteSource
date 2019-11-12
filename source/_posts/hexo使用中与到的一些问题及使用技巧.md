---
title: hexo使用中与到的一些问题及使用技巧
date: 2019-11-11 14:49:38
tags: hexo
---

# hexo使用中与到的一些问题及使用技巧

## 1. 默认会用相对路作为标题

如果_posts中有多级目录的话, **默认会用相对路作为标题**, 如`java/java基础`. 
这就需要在文章头的 front-matter 中, 要加上`title`参数, 此时就会使用title中的名字作为标题

## 2. 创建文件时生成front-matter信息 

使用`hexo new [文件名]`的方式会默认使用scaffolds中的post模板生成文件

## 3. 摘要显示图片

默认的方式是front-matter中添加`phothos`, 但是试了一下会报错, 目前不知道原因
现在通过修改`post.js`文件(*摘要的显示需要修改这个文件, 现在摘要的显示也是修改后的*), 添加`conver`来显示图片