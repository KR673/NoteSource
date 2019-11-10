---
tags: "hexo"
---

[toc]

# 1. github

## 1.1 创建仓库

**注意** 这个名字最好的`用户名.github.io`, 因为之后使用hexo生成的静态文件中会使用 `/css/index.css`作为css的相对路径, 如果使用其他名字, github生成的网站地址会多出两级目录,导致找不到css和js文件

![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191110222817.png)

## 1.2 设置仓库

在仓库的设置中设置GitHub Pages 为 master

![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191110223555.png)

# 2. hexo

## 2.1 安装

> 依照hexo的官方首页命令安装

## 2.2 布署

### 2.2.1 生成静态文件

执行 : `hexo generate` 或 `hexo g`

### 2.2.2 上传到github

* 修改根目录下的_config.yml文件, repository改为刚刚创建的Github仓库SSh链接

    ```
    deploy:
    type: git
    repository: git@github.com:KR673/note.github.io.git
    branch: master
    ```
    **注意**这个repository使用**SSH链接**而不是https

* 执行 : `hexo deploy` 或 `hexo d`

## 2.3 常用hexo命令

```
hexo new "postName" #新建文章
hexo new page "pageName" #新建页面
hexo generate #生成静态页面至public目录
hexo server #开启预览访问端口（默认端口4000，'ctrl + c'关闭server）
hexo deploy #部署到GitHub
hexo help  # 查看帮助
hexo version  #查看Hexo的版本
```

缩写：

```
hexo n == hexo new
hexo g == hexo generate
hexo s == hexo server
hexo d == hexo deploy
```

组合命令：

```
hexo s -g #生成并本地预览
hexo d -g #生成并上传
```