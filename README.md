# WordPress 项目

## 简介

采用docker容器搭建网站(mysql, nginx,php,wordpress).

## 容器

整体长期运行3个docker container。

### nginx

- 作为接收路由转发

### php

- php作为wordpress运行

### mysql

- mysql用于存放数据

另外,还有一个php包含wp-cli的运行调试container，用在需要命令行调试时候.

## 目录

### mysql

- 空文件夹,用于mysql的container挂载本地目录.

- 后期备份blog可以只复制这个目录.

### wordpress

- 存放从wordpress官方下载(zip/gz)文件解压的wordpress源码文件
- php的container挂载此目录，运行wordpress

### nginx(default.conf)

- 存放代理配置信息, 两个地方需要定制:
  - 网站配置文件，**域名对应**；
  - certs存放ssl证书文件，与default.conf中的**路径匹配**.
