---
title: Ubuntu-22.04配置远程登录
categories:
  - 系统
  - Ubuntu
tags:
  - ubuntu
date: 2023-06-26 02:31:58
---

# 步骤

## 1. 修改配置文件

```bash
$ vi /etc/ssh/sshd_config
```

![image-20230626023446041](https://cdn.myshenle.top/images/202306260234098.png)

## 2. 重启服务

```bash
$ service sshd restart
$ service sshd status
```

