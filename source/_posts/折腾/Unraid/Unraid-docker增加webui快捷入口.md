---
title: Unraid-docker增加webui快捷入口
categories:
  - 折腾
  - Unraid
tags:
  - unraid
date: 2023-06-26 23:48:48
---

# br0 模式

br0 模式 docker 拥有独立 ip，需要手动指定 ip 和端口

设置：

![手动指定WebUI](http://cdn.myshenle.top/images/202306262349727.png)

效果：

![图标有了快捷入口](http://cdn.myshenle.top/images/202306262351589.png)

# 端口映射模式

Brigde 主机端口和容器端口可能不一致

