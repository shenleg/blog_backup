---
title: Docker-错误
categories:
  - 工具
  - Docker
tags:
  - docker
date: 2023-07-04 11:36:25
---



su: must be suid to work properly

解决：

1. 以 root 用户进入容器：`docker exec -it --user root containername bash or sh`
2. 修改 busybox 权限：`chmod 4755 /bin/busybox`

