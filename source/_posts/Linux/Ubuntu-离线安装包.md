---
title: Ubuntu-离线安装包
categories:
  - 系统
  - Linux
tags:
  - Ubuntu
date: 2023-05-30 01:36:50
---

# 需求

离线情况下无法使用 apt install 安装包

# 步骤

新建一个文件夹，专门保存下载的软件包

```bash
$ mkdir offline_package
$ cd offline_package
```

下载离线包，packagename 换成要下载包名

```bash
$ sudo apt-get download $(apt-cache depends --recurse --no-recommends --no-suggests --no-conflicts --no-breaks --no-replaces --no-enhances <packagename> | grep "^\w" | sort -u)
```

修改权限，建立依赖关系

```bash
$ mkdir ./archives
$ dpkg-scanpackages ./ /dev/null | gzip > ./archives/Packages.gz -r
$ sudo chmod 777 -R ./
```

如果出现错误：sudo:dpkg-scanpackages: command not found，则需要安装dpkg-dev工具

```bash
$ sudo apt install dpkg-dev
```

打包文件夹

```bash
$ tar -czvf ../offline_package.tar.gz ../offline_package
```

将打包后的文件拷贝到离线服务器上并解压，比如我们放到 root 目录下

```bash
$ tar -xzvf test.tar.gz
$ cd offline_package/archives
$ gzip -d Packages
```

修改源

```bash
$ sudo mv /etc/apt/sources.list /etc/apt/sources.list.bak
$ sudo echo "deb [trusted=yes] file:///root/offline_package/ archives/" > /etc/apt/sources.list
```

更新源

```bash
$ sudo apt update
```

安装软件包

```bash
$ sudo apt install <packagename>
```

如果提示依赖问题，可以使用下边的命令修复

```bash
$ sudo apt install -f
```

恢复源

```bash
$ sudo mv /etc/apt/sources.list.bak /etc/apt/sources.list
$ sudo apt update
```



# 参考

* [Linux之ubuntu离线安装软件包](https://blog.csdn.net/zong596568821xp/article/details/105994450)
