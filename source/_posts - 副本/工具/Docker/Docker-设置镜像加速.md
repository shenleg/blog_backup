---
title: Docker-设置镜像加速
categories:
  - 工具
  - Docker
tags:
  - docker
date: 2023-06-21 23:21:25
---

# 需求

docker 默认拉取服务器在国外，速度会很慢。需要更改默认镜像源

# 步骤

## 国内镜像服务器

* 科大镜像：https://docker.mirrors.ustc.edu.cn/
* 网易云：https://hub-mirror.c.163.com/
* 腾讯云：https://mirror.ccs.tencentyun.com
* 七牛云：https://reg-mirror.qiniu.com/
* 阿里云：https://<你的ID>.mirror.aliyuncs.com，推荐

阿里云镜像获取地址：https://cr.console.aliyun.com/cn-hangzhou/instances/mirrors，登录后，左侧菜单选中镜像加速器就可以看到你的专属地址。



## docker 设置

```
$ sudo mkdir -p /etc/docker
$ sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://mw2h67da.mirror.aliyuncs.com"]
}
EOF

$ sudo systemctl daemon-reload
$ sudo systemctl restart docker
```



## 检查是否生效

```
$ docker info
 Registry Mirrors:
  https://mw2h67da.mirror.aliyuncs.com/
```

# 参考

* [Docker 镜像加速 | 菜鸟教程 (runoob.com)](https://www.runoob.com/docker/docker-mirror-acceleration.html)
