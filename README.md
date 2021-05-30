# Megumi-bot
# 前言：憨憨机器人，搭建在本地arm64 r2s的openwrt，docker内，谨慎参考
#由于只会用openwrt，于是在opt安装docker  用dockers安装centos7部署go-cqhttp
n#odejs一直装不上，索性又在docker里装notejs，docker版来部署cq-picsearcher-bot

&nbsp;

## 准备：拉取部署CentOS_7、node.jsPython

1. 使用docker拉取centos7；node.js；python镜像（不用rss可以不下python）
```
    `Docker pull centos:7`      
    ```
    `Docker pull node:latest`       
    ```
    `Docker pull python:latest`     
```
2. 创建容器centos7&nodejs&python

    `docker run --restart always -itd --net host --name go centos:7 /bin/bash`      
    `docker run --restart always -itd --net host --name pic node:latest /bin/bash`      
    `docker run --restart always -itd --net host --name rss python:latest /bin/bash`        

 __*查看容器运行状态__

`docker ps`

## go-cqhttp配置安装

1. 访问容器内centos7

    `docker exec -it go/ bin/bash`

2. 安装wget,git,screen这几个命令

    `yum install -y wget git screen`

__开始部署go-cqhttp__

1. 新建窗口

    `screen -S qq`

2. 新建文件夹并进入

    `mkdir go-cqhttp && cd go-cqhttp`

3. 访问go-cqhttp的[[releases]](https://github.com/Mrs4s/go-cqhttp/releases)页面获取最新版本
右键 go-cqhttp_linux_arm64.tar.gz 复制下载链接

    `wget [粘贴链接]`

 ~~什么 下载不了?那你怎么访问的GitHub~~
 
    `tar -zxvf go-cqhttp_linux_arm64.tar.gz`        
    `chmod -R 700 ./go-cqhttp`

 4. __需要运行一遍使其生成默认配置文件__
* 新开个窗口重新进入centos7~~不知到怎么退出screen -S qq~~

* 重新访问centos

    `docker exec -it go/ bin/bash`
  
* 首次运行__选择2.正向WS__

 ``` 
 ./go-cqhttp/go-cqh择2.正向WSttp faststar
 ```
 草
 
 
