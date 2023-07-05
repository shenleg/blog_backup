---
title: Unraid-Docker设置
categories:
  - 折腾
  - Unraid
tags:
  - unraid
date: 2023-07-03 21:41:48
---

# 需求



# 步骤

![docker设置](http://cdn.myshenle.top/images/202307032228075.png)

说明：

* Docker-data-root：
* Docker 虚拟磁盘大小：随时可调整
* Docker 虚拟磁盘位置：所有容器本身磁盘存储位置，可直接备份
* 默认应用数据存储位置：所有容器数据磁盘存储位置，可直接备份
* 模板创作模式：
* Docker 自定义网络类型：ipvlan（和 unraid 共用 mac） 和 macvlan（真实桥接物理网络）
* 主机访问自定义网络：可以从 unraid 访问容器，某些情况下需要打开（内网穿透客户端在 unraid）
* 保留用户定义网络：保留自定义创建的网络
* 接口上 IPv4 自定义网络 br0：docker 网络多一个 br0，可以桥接到物理网络

# 参考
