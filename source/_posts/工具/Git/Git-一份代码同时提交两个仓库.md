---
title: Git-一份代码同时提交两个仓库
categories:
  - 工具
  - Git
tags:
  - Git
date: 2023-05-25 01:42:19
---

# 绑定多个远端仓库

绑定第一个仓库，能够正常推送拉取

```bash
$ git remote add orgin https://gitee.com/enilu/material-admin.git
```

绑定第二个仓库，只做推送

```bash
$ git remote set-url --add origin https://github.com/enilu/material-admin.git
```

这个时候查看远端仓库信息会有两个 Push 的远程仓库

```bash
$ git remote -v
orgin   https://github.com/MeterosBehind/MyJava.git (fetch)
orgin   https://github.com/MeterosBehind/MyJava.git (push)
orgin   https://gitee.com/youngforever1728/my-java.git (push)
```

之后再进行 add commit push 即可，会将代码同时 Push 到两个远程仓库中

