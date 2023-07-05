---
title: Alpine
categories:
  - 系统
  - Linux
tags:
  - alpine
date: 2023-07-04 10:43:41
---

# 介绍

Alpine是一个社区开发的面向安全应用的轻量级 Linux 发行版。 Alpine 的意思是“高山的”，它采用了 musl libc 和 busybox 以减小系统的体积和运行时资源消耗，同时还提供了自己的包管理工具 apk。

Alpine Docker 镜像也继承了 Alpine Linux 发行版的这些优势。相比于其他 Docker 镜像，它的容量非常小，仅仅只有 5 MB 左右，且拥有非常友好的包管理机制。官方镜像来自 docker-alpine 项目。

由于其小巧、安全、简单以及功能完备的特点，被广泛应用于众多Docker容器中。

# 包管理

## 镜像源配置

官方镜像源列表：[dl-cdn.alpinelinux.org/alpine/MIRRORS.txt](http://dl-cdn.alpinelinux.org/alpine/MIRRORS.txt)

国内镜像源：

* 清华TUNA镜像源：https://mirror.tuna.tsinghua.edu.cn/alpine/
* 中科大镜像源：http://mirrors.ustc.edu.cn/alpine/
* 阿里云镜像源：http://mirrors.aliyun.com/alpine/

配置镜像源：

```shell
$ vi /etc/apk/repositories
http://mirrors.ustc.edu.cn/alpine/v3.15/main/
http://mirrors.ustc.edu.cn/alpine/v3.15/community/
```

注意版本对应：

```shell
$ cat /etc/os-release
NAME="Alpine Linux"
ID=alpine
VERSION_ID=3.15.0
PRETTY_NAME="Alpine Linux v3.15"
HOME_URL="https://alpinelinux.org/"
BUG_REPORT_URL="https://bugs.alpinelinux.org/"
```



## apk包管理命令

* `apk --help`：查看完整的包管理命令
* `apk info`：列出所有已安装的软件包
  * `apk info package`：列出指定已安装的软件包信息
* `apk update`：更新最新镜像源列表
* `apk upgrade`：升级所有软件包
  * `apk upgrade package`：升级指定软件包
  * `apk upgrade package1 package2`：升级多个软件包
* `apk search`：搜索所有可用软件包，搜索之前最好先更新镜像源
  * `apk search -v`：查找所有可用软件包及其描述内容
  * `apk search package`：查找指定软件包
* `apk add`：从仓库中安装最新软件包，并自动安装必须的依赖包
  * `apk add package`：安装指定软件包
  * `apk add package1 package2`：安装多个软件包
  * `apk add --no-cache package`：不使用本地镜像源缓存，相当于先执行 update，再执行 add
* apk del package：卸载并删除指定软件包

常用软件：`apk add bash wget curl git make vim`



# 服务管理

# 参考

* [Alpine Linux_夜风轻快的博客-CSDN博客](https://blog.csdn.net/m0_50111062/article/details/126632800)

