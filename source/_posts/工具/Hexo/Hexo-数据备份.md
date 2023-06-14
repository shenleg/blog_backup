---
title: Hexo-数据备份
categories:
  - 工具
  - Hexo
tags:
  - hexo
date: 2023-05-25 15:53:28
---

# 需求

防止博客原始数据丢失。

博客内容已上传到 Github Page（不重要，有原始数据就可以再生成），需要备份博客原始数据。

# 步骤

## 1. 初始化 git 仓库

在博客根目录下初始化 git 仓库


## 2. 配置 git 仓库

不需要备份所有文件，创建 `.gitignore` 排除文件

```
.DS_Store
*.log
db.json

.deploy_git/
.git/
.github/

node_modules/
public/
```

Github 和 Gitee 创建备份仓库，双重备份

添加两个远程仓库，参考《Git-一份代码同时提交两个仓库》

## 3. 配置命令别名

写入到配置文件中，生效一下

```
alias hn='hexo new post'
alias hs='hexo clean && hexo g && hexo s --debug'
alias hd='hexo clean && hexo g && hexo d && git add . && git commit -m "update" && git push -f'
```

## 4. 测试

此时执行 hd 命令即可：部署博客&备份博客原始数据

妈妈再也不用担心我的博客丢失啦

TODO：markdown 中的外链也需要定期备份

