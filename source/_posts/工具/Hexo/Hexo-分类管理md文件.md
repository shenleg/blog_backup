---
title: Hexo-分类管理md文件
categories:
  - 工具
  - Hexo
tags:
  - hexo
date: 2023-05-25 11:44:25
---

# 需求

通过 `hexo new` 创建的文章默认统一在 `source/_posts` 文件夹下，文章多了之后容易找不到和冲突

需要更改配置，分类管理文章

# 步骤

## 1. 年月分类

在`_config.yml`文件中修改下面的命令，使默认创建的文章按照年月分类
`new_post_name: :year/:month/:title.md`

```bash
$ hexo new post test1
INFO  Validating config
INFO  Created: ~/Documents/Hexo/source/_posts/2023/05/test1.md
```



## 2. 自定义分类

```bash
$ hexo new post -p 后端/test2
INFO  Validating config
INFO  Created: ~/Documents/Hexo/source/_posts/后端/test2.md
```

# 配置

## 旧文章处理

在 `source/_posts` 文件夹手动分类，重新生成部署即可

# 参考

* [hexo博客文章多了怎么管理](https://blog.csdn.net/weixin_40251892/article/details/107590794)

