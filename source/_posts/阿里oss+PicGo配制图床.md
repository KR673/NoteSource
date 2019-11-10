---
tags: "图床"
---
[toc]

## 1. 购买阿里oss

按流量 / 包月, 按需购买即可, **此处购买的只是空间, 流量另外付费**

### 1.1 获取AccessKeys

![0](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191110012222.png)
***
> 以下为RAM访问控制, 设置这个子用户更加的安全
![1](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191110005443.png)
![2](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191110010153.png)

## 2 下载并配制PicGo

### 2.1 下载

[下载地址](https://github.com/Molunerfinn/PicGo/releases)

### 2.2 配制

![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191110010937.png)

* accesskey和accesskeySecret可以从阿里云控制台获取(刚刚设置的)。
* 存储空间名是bucket的名字。
* 存储区域到阿里云OSS控制台去找，例如下图中存储区域就是 `oss-cn-beijing`
![](https://mynoteimg.oss-cn-beijing.aliyuncs.com/20191110010639.png)
* 存储路径是存储图片的位置，要求以/结尾,bucket中没有指定文件夹的话可以不填。
* 自定义域名可以不填写。