---
title: Unraid-安装OpenWrt
categories:
  - 折腾
  - Unraid
tags:
  - unraid
date: 2023-06-28 23:04:48
---

# 需求



# 步骤

前置：将网站添加进 cloudflare

1. 打开 [Cloudflare](https://dash.cloudflare.com/) 控制台
1. 左侧点击 Zero Trust
1. 选择免费的计划，添加付款方式 - 推荐 PayPal
1. 在 Access Tunnels 中，点击 Access - Tunnels 创建一个 Tunnel
1. 配置 Tunnel 选择 docker 方式

   ```
   docker run -d \
   --name cloudflared \
   --net br0 \
   --restart unless-stopped \
   cloudflare/cloudflared:latest \
   tunnel --no-autoupdate run \
   --token <YourToken>
   ```

1. 配置域名和转发 URL

# 参考

* [UnRaid虚拟机安装OpenWrt软路由](https://blog.csdn.net/engineerlzk/article/details/128337964)
