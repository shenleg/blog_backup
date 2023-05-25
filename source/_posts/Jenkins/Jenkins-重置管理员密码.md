---
title: Jenkins-重置管理员密码
categories:
  - 工具
  - Jenkins
tags:
  - Jenkins
date: 2023-05-25 09:52:37
---

# 需求

Jenkins admin 用户忘记密码，需要重置密码

# 步骤

## 1. 修改配置文件

修改 Jenkins 目录的 `config.xml`文件，通常在 `~/.jenkins/config.xml`

修改 `useSecurity` 字段为 `false`，然后重新启动 Jenkins。你就会发现不需要登陆也能进入管理页面。

重启 Jenkins

## 2. 修改 Jenkins 配置

直接进入 Jenkins 后台 -> 系统管理 -> 全局安全配置

此操作可出现 `管理用户` 模块

![全局安全配置](https://cdn.myshenle.top/images/202305251012933.png)

## 3. 修改密码

直接进入 Jenkins 后台 -> 系统管理 -> 管理用户

![重置用户密码](https://cdn.myshenle.top/images/202305251021368.png)

恢复 `Jenkins` 配置（自动设置 `config.xml` ），重启 Jenkins，登录验证

![恢复 Jenkins 配置](https://cdn.myshenle.top/images/202305251045781.png)

# 参考

* [Jenkins 官方](https://www.jenkins-zh.cn/tutorial/management/auth/lost-password/)
* [Jenkins之忘记管理员账户密码重置方法](https://blog.csdn.net/carefree2005/article/details/112169302)
