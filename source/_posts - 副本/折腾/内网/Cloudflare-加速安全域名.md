---
title: Cloudflare-加速安全域名
categories:
  - 折腾
  - 内网
tags:
  - cloudflare
date: 2023-06-29 00:35:48
---

# 需求

加快域名访问速度（DNS解析、CDN），提高安全性

# 步骤

## 将网站添加进 cloudflare

1. 打开 [Cloudflare](https://dash.cloudflare.com/) 控制台
2. 左侧点击网站
3. 点击添加站点，输入自己的域名（不包含 www）
4. 选择免费计划
5. 等待扫描，查看 DNS 记录

## 更改域名服务器为 cloudflare

1. 登录域名注册机构。这里以阿里云为例
2. 域名选择管理 - DNS管理 - DNS修改
3. 修改为 cloudflare 的 DNS服务器，等待 5min-48h。
4. 成功：Cloudflare 正在保护您的站点

## 快速入门指南

1. 自动、始终 https
2. Brotli 压缩
3. 完成

# 应用

1. 可以监控网站数据
2. 可以直接添加域名解析，不再需要阿里云

# 参考

* [Cloudflare域名解析接入，免费使用DNS和CDN_哔哩哔哩_bilibili](https://www.bilibili.com/video/BV1MV4y1D7eR/)
