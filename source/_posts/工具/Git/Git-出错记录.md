---
title: Git-错误记录
categories:
  - 工具
  - Git
tags:
  - Git
  - 错误
date: 2023-06-15 11:36:11
---



问题：fatal: 位于未检出的子模组

常见于git项目中还有git项目，发生了嵌套

```shell
$ git rm --cache <子模块路径名称>
```

