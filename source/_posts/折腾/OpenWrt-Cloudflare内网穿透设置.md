---
title: Unraid-安装OpenWrt
categories:
  - 折腾
  - Unraid
tags:
  - unraid
date: 2023-06-29 02:24:48
---

# 需求

# 步骤

1. 系统-软件包-刷新列表（或者命令行执行 opkg update）

1. 下载 cloudflared 软件包

1. 启用插件

   ![启用插件](https://cdn.myshenle.top/images/202306290238027.png)

   

1. 登录 cloudflared 账号授权域名

   ![授权域名](https://cdn.myshenle.top/images/202306290250249.png)

1. 复制ca证书到 cloudflare 配置文件夹
   ![复制证书](https://cdn.myshenle.top/images/202306290253286.png)

1. 创建隧道，复制配置文件
   ![创建隧道](https://cdn.myshenle.top/images/202306290257065.png)

1. 修改配置文件
   ![修改配置文件](https://cdn.myshenle.top/images/202306290259148.png)

1. 重启 cloudflare 服务：/etc/init.d/cloudflared restart

1. 验证
   ![创建隧道成功](https://cdn.myshenle.top/images/202306290301031.png)

1. 配置隧道
   ![image-20230629030324799](https://cdn.myshenle.top/images/202306290303825.png)

   ![一直确定下一步](https://cdn.myshenle.top/images/202306290303584.png)

1. 重新进入隧道配置页面，可以开始添加本地服务器映射了

   ![本地映射](https://cdn.myshenle.top/images/202306290308476.png)

1. 2

1. 3

1. 4

1. 5

1. 6

# 参考

* [UnRaid虚拟机安装OpenWrt软路由](https://blog.csdn.net/engineerlzk/article/details/128337964)
