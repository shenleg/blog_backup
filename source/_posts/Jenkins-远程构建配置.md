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

![远程构建配置](https://cdn.myshenle.top/images/202305251103963.png)

## 2. 调用测试

可直接在浏览器地址栏输入调用

* 无参数：`JENKINS_URL/job/test/build?token=TOKEN`
* 有参数：`JENKINS_URL/job/test/buildWithParameters?token=TOKEN&param1=value1`

`JENKINS_URL` 为 Jenkins 访问地址

# 参考

* [JENKINS触发远程构建功能使用](https://www.jianshu.com/p/aa0dc1157599)

