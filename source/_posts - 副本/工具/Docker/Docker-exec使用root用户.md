---
title: Docker-exec使用root用户
categories:
  - 工具
  - Docker
tags:
  - docker
date: 2023-07-04 11:23:25
---

# 需求

使用 `docker exec -it 容器 bash` 进入容器发现不是 root 用户，且没有 sodo、权限拒绝等

# 步骤

```
$ docker exec -it --user root containername bash or sh
$ whoami
root
```

# 参考

* [How to run bash as user root on alpine images with docker? su: must be suid to work properly - Stack Overflow](https://stackoverflow.com/questions/61683448/how-to-run-bash-as-user-root-on-alpine-images-with-docker-su-must-be-suid-to-w)
* [docker 进入容器执行su命令报 su: must be suid to work properly_docker must be suid to work properly_戴国进的博客-CSDN博客](https://blog.csdn.net/JineD/article/details/114410937)

