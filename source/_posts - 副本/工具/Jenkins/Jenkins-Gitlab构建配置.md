---
title: Jenkins-Gitlab构建配置
categories:
  - 工具
  - Jenkins
tags:
  - Jenkins
date: 2023-05-25 10:58:19
---

# 需求

推送代码、合并代码即可构建应用，不需要进入页面手动点击

# 步骤

## 1. Jenkins 配置

### 1.1 安装插件

gitlab

### 1.2 job 配置

被触发构建的项目 -> 构建触发器 -> Build when a change is pushed to GitLab 勾选

![](http://cdn.myshenle.top/images/202210241508278.png)

往下拉，高级设置：

![](http://cdn.myshenle.top/images/202210241510419.png)

此处可过滤分支 `Allowed branches`

## 2. Gitlab 配置

### 2.1 项目配置

触发构建的项目 -> Setting -> Webhooks -> Add webhook

![webhook 设置](http://cdn.myshenle.top/images/202210241544320.png)


### 异常情况

如果 jenkins 和 gitlab 都在同一台服务器上，可能会弹出警告阻止添加

![异常警告](http://cdn.myshenle.top/images/202210241700683.png)

需要设置允许本地 webhook，修改完后需要再次 Add webhook

![设置允许本地 webhook](http://cdn.myshenle.top/images/202210241549052.png)

## 3. 测试

模拟推送事件

![推送测试](http://cdn.myshenle.top/images/202210241703013.png)

![成功提示](http://cdn.myshenle.top/images/202210241702712.png)

查看 Jenkins

![成功运行](http://cdn.myshenle.top/images/202210241704772.png)

# 参考

* [Gitlab触发jenkins构建](https://blog.csdn.net/ownfire/article/details/124766548)
