---
title: Unraid-安装OpenWrt
categories:
  - 折腾
  - Unraid
tags:
  - unraid
date: 2023-06-28 02:40:48
---

# 准备

1. 开启虚拟机功能
2. 下载镜像
3. 上传镜像，上传至 /mnt/user/ioso 目录（专门放置虚拟机镜像的文件夹），解压

# 安装步骤

## 1. 添加虚拟机

![image-20230628014641544](https://cdn.myshenle.top/images/202306280146578.png)

![image-20230628014840940](https://cdn.myshenle.top/images/202306280148966.png)

## 2. 配置虚拟机

* 稍等几分钟直接登录系统
* 输入 `vi /etc/config/network` 更改 LAN IP

![ip config](https://cdn.myshenle.top/images/202306280300604.png)

## 3. 重启虚拟机

* `reboot`
* 输入刚才配置的 LAN IP 登录后台

# 配置

1. 浏览器输入刚才设置的 ip
2. 输入默认密码登录配置



# 参考

* [UnRaid虚拟机安装OpenWrt软路由](https://blog.csdn.net/engineerlzk/article/details/128337964)
