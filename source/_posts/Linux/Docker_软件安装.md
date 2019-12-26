---
title: Docker_软件安装
date: 2019-12-26 23:03:05
tags: 
    - docker
    - linux
    - tomcat
    - nginx
---

[toc]

## 1. 软件安装

**常用命令**:

* 搜索镜像 : `docker search <name>` 
* 查看下载的镜像 : `docker images`
* 查看运行中的容器 : `docker ps` / `docker ps -a`
* 启动容器 : `docker run <option> <argument>`
   * -d 后台启动
   * -p 端口映射
   * -v 将主机中的目录挂载到容器
* 进入容器 : `docker exec -it <name> bash`
* 重启容器 : `docker restart <name>`
* 停止容器 : `docker stop <name>`
* 删除容器 : `docker rm <name>`

### 1.1 tomcat安装

1. 下载镜像 : `docker pull tomcat`
2. 启动容器 : `docker run -d -p 8080:8080 -v /opt/tomcat/webapps:/usr/local/tomcat/webapps/test tomcat:latest`
   > 将主机中的目录/opt/tomcat/webapps的/test下, *注意不要挂载到容器的webapps下, 这样会webapps会做为一个空目录,配制文件丢失*

参考 : 
1. <https://www.runoob.com/docker/docker-install-tomcat.html>

### 1.2 nginx安装