---
title: OpenWrt-Cloudflare内网穿透设置
categories:
  - 折腾
  - OpenWrt
tags:
  - openwrt
date: 2023-06-29 02:24:48
---

# 需求

让 cloudflare 穿透服务运行在 OpenWrt 上，从而可通过二级域名进行安全的内网访问

# 步骤

1. 系统-软件包-刷新列表（或者命令行执行 opkg update）

1. 下载 cloudflared 软件包

1. 启用插件

   ![启用插件](https://cdn.myshenle.top/images/202306290238027.png)

   

1. 登录 cloudflared 账号授权域名，生成 ca 证书

   ![授权域名](https://cdn.myshenle.top/images/202306290250249.png)

1. 复制 ca 证书到 cloudflare 配置文件夹
   ![复制证书](https://cdn.myshenle.top/images/202306290253286.png)

1. 创建隧道，复制隧道文件
   ![创建隧道](https://cdn.myshenle.top/images/202306290257065.png)

1. 修改配置文件
   ![复制隧道id到配置文件](https://cdn.myshenle.top/images/202306290259148.png)

1. 重启 cloudflare 服务：/etc/init.d/cloudflared restart

1. 验证
   ![创建隧道成功](https://cdn.myshenle.top/images/202306290301031.png)

1. 配置隧道
   ![配置隧道](https://cdn.myshenle.top/images/202306290303825.png)

   ![同步隧道配置](https://cdn.myshenle.top/images/202306290303584.png)

1. 重新进入隧道配置页面，可以开始添加本地服务器映射了

   ![本地映射](https://cdn.myshenle.top/images/202306290308476.png)

# 参考

