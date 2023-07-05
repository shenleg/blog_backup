---
title: Jenkins-远程构建配置
categories:
  - 工具
  - Jenkins
tags:
  - Jenkins
date: 2023-05-25 10:57:58
---

# 需求

通过 Http 请求即可构建应用，不需要进入页面手动点击，支持参数构建

# 步骤

## 1. job 配置

![远程构建配置](http://cdn.myshenle.top/images/202305251103963.png)

## 2. 调用测试

可直接在浏览器地址栏输入调用

* 无参数：`JENKINS_URL/job/test/build?token=TOKEN`
* 有参数：`JENKINS_URL/job/test/buildWithParameters?token=TOKEN&param1=value1`

`JENKINS_URL` 为 Jenkins 访问地址

# 配置

## 匿名用户权限

不需要登录即可构建，配置匿名用户的调用权限

进入：系统设置 -> 全局安全配置

![匿名用户权限配置](http://cdn.myshenle.top/images/202305251120076.png)

# 参考

* [JENKINS触发远程构建功能使用](https://www.jianshu.com/p/aa0dc1157599)

