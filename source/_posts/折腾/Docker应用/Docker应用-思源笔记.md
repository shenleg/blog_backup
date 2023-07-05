---
title: Docker应用-思源笔记
categories:
  - 折腾
  - Docker应用
tags:
  - docker
date: 2023-06-27 00:46:48
---

# 地址

* GitHub：[siyuan-note/siyuan: A privacy-first, self-hosted, fully open source personal knowledge management software, written in typescript and golang. (github.com)](https://github.com/siyuan-note/siyuan)



# 安装

* 创建本地映射文件夹：mkdir -p /mnt/user/appdata/siyuan/workspace
* 修改用户组：cd /mnt/user/appdata & chown -R 1000:1000 siyuan/workspace
* docker 安装

```shell
docker run -d \
--name='siyuan' \
--net='br0' \
--ip='10.1.1.101' \
-u 1000:1000 \
-v '/mnt/user/appdata/siyuan/workspace':'/siyuan/workspace':'rw' \
-l net.unraid.docker.webui='http://10.1.1.101:6806' \
-l net.unraid.docker.icon='http://cdn.myshenle.top/images/202307031907903.png' \
b3log/siyuan:v2.9.4 \
--workspace='/siyuan/workspace' \
--lang='zh_CN' \
--accessAuthCode='123456'
```

* 说明：
  * `--workspace` 指定工作空间文件夹路径，在宿主机上通过 `-v` 挂载到容器中
  * 镜像中是使用默认创建的普通用户 `siyuan`（uid 1000/gid 1000）来启动内核进程的，所以在宿主机创建工作空间文件夹时请注意设置该文件夹所属用户组：`chown -R 1000:1000 /siyuan/workspace`，在启动容器时需要带参数 `-u 1000:1000`

* 查看帮助：`docker exec -it siyuan /opt/siyuan/kernel --help`

更多参数：

* accessAuthCode string：access auth code
* lang string：zh_CN/zh_CHT/en_US/fr_FR/es_ES
* port string：port of the HTTP server (default "0")
* readonly string：read-only mode (default "false")
* workspace string：dir path of the workspace, default to ~/SiYuan/



# 使用



# 升级



# 参考

* [使用docker搭建多端同步思源笔记_NAS存储_什么值得买 (smzdm.com)](https://post.smzdm.com/p/am8m09gz/)
* [Docker部署思源笔记, 数据自己掌握_NAS存储_什么值得买 (smzdm.com)](https://post.smzdm.com/p/a0qro908/)
* [【教程】使用docker搭建WebDAV服务_docker webdav_GUSONGEN的博客-CSDN博客](https://blog.csdn.net/u011459717/article/details/128758573)
* [用思源笔记打造高效写作笔记系统（一） - 知乎 (zhihu.com)](https://zhuanlan.zhihu.com/p/370780955)