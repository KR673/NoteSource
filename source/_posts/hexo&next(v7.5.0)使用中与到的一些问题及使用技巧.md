---
title: hexo&next(v7.5.0)使用中与到的一些问题及使用技巧
date: 2019-11-11 14:49:38
tags: 
    - hexo
    - next
---

# hexo&next(v7.5.0)使用中与到的一些问题及使用技巧

## 1. hexo

### 1.1 默认会用相对路作为标题

如果_posts中有多级目录的话, **默认会用相对路作为标题**, 如`java/java基础`. 
这就需要在文章头的 front-matter 中, 要加上`title`参数, 此时就会使用title中的名字作为标题

### 1.2 创建文件时生成front-matter信息 

使用`hexo new [文件名]`的方式会默认使用scaffolds中的post模板生成文件

### 1.3 左侧添加标签云

1. [插件地址](https://github.com/MikeCoder/hexo-tag-cloud)
2. [参考](https://blog.csdn.net/Aoman_Hao/article/details/89416634)

修改模板文件的时候需要加在里面
![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191113203229.png)

## 1.4 根据目录结构生成分类

1. [插件地址](https://github.com/xu-song/hexo-auto-category)
2. [参考](https://blog.eson.org/pub/e2f6e239/)

注意修改的是根目录的配制文件

## 2. next

### 2.1 摘要显示图片

默认的方式是front-matter中添加`phothos`, 但是试了一下会报错, 目前不知道原因
现在通过修改`post.js`文件(*摘要的显示需要修改这个文件, 现在摘要的显示也是修改后的*), 添加`conver`来显示图片

### 2.2 文章添加版权声明

设置config中的 `creative_commons`, post 改为 true
![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191113105946.png)

### 2.3 添加gitalk评论

<https://segmentfault.com/a/1190000014085547>