---
title: Docker应用-青龙面板
categories:
  - 折腾
  - Docker应用
tags:
  - docker
date: 2023-06-27 00:46:48
---

# 地址

* DockerHub：[whyour/qinglong - Docker Image | Docker Hub](https://hub.docker.com/r/whyour/qinglong)
* GitHub：[whyour/qinglong: 支持 Python3、JavaScript、Shell、Typescript 的定时任务管理平台](https://github.com/whyour/qinglong)
* GitHub：[FlechazoPh/QLDependency: 青龙面板全依赖一键安装脚本)](https://github.com/FlechazoPh/QLDependency)
* GitHub：[shufflewzc/faker2: 不破楼兰终不还 (github.com)](https://github.com/shufflewzc/faker2)



# docker 安装

注意 latest 不一定是最新的

```bash
docker run -d \
--name qinglong \
--net br0 \
--ip '10.1.1.100' \
-v /mnt/user/appdata/qinglong/data:/ql/data \
whyour/qinglong:latest
```

登录设置通知和用户名密码

# 安装依赖

# 安装库



