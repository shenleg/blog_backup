---
title: Ubuntu-换源
categories:
  - 系统
  - Ubuntu
tags:
  - Ubuntu
date: 2023-05-30 01:35:41
---

# 需求

下载慢

# 步骤

1. 备份源文件

   ```bash
   $ sudo cp /etc/apt/sources.list /etc/apt/sources.list.bk
   ```

2. 修改源

   ```bash
   $ sudo vi /etc/apt/sources.list
   ```

   参考：[清华源自助替换](https://mirror.tuna.tsinghua.edu.cn/help/ubuntu/)。注意：版本要对应，查看版本：`lsb_release -a`

3. 更新索引

   ```bash
   $ sudo apt update
   ```

# 参考

* [ubuntu换源](https://blog.csdn.net/qq_45878098/article/details/126037838)

