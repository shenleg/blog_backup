---
title: Gitlab-重置管理员密码
categories:
  - 工具
  - Gitlab
tags:
  - Gitlab
date: 2023-05-25 12:35:41
---

# 需求

Gitlab root 用户忘记密码，需要重置密码

# 步骤

1. 重置 root 密码之前，需先使用 root 用户登录到 gitlab 所在服务器
    `gitlab-rails console -e production`
2. 等待控制台加载完毕，有多种找到用户的方法
    * 通过用户名：`user = User.find_by_username 'exampleuser'`
    * 通过用户 ID：`user = User.find(123)`
    * 通过 email：`user = User.find_by(email: 'user@example.com')`
3. 输入新密码（须符合最低8位限制）：`user.password = '新密码'`
4. 确认密码：`user.password_confirmation = '新密码'`
5. 保存更改：`user.save!`
6. 退出：`exit`
7. 用新密码登录验证

![详细步骤](http://cdn.myshenle.top/images/202210171421655.png)

# 参考

* [官方文档说明](https://docs.gitlab.com/ee/security/reset_user_password.html)
