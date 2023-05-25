---
title: Hexo-添加看板娘
categories:
  - 工具
  - Hexo
tags:
  - hexo
date: 2023-05-25 15:53:28
---

# 低级看板娘安装步骤

没有更多自定义功能

## 1. 安装动画

如果安装过要先卸载 `npm uninstall hexo-helper-live2d`

```bash
$ npm install --save hexo-helper-live2d
```

## 2. 安装模型

```bash
$ npm install live2d-widget-model-模型名称
```

模型名称可在 `node_modules/live2d-widget/README.md` 找到，推荐 `shizuku`

## 3. 配置

修改 Hexo 的配置文件 `_config.yml`

```yaml
## Live2D看板娘
live2d:
  enable: true
  pluginModelPath: assets/
  model:
    # 模板目录，在node_modules里
    use: live2d-widget-model-shizuku  
  display:
    position: right
    width: 300 
    height: 600
  mobile:
    # 在手机端显示
    show: false   
  rect:
    opacity:0.7
```

重新部署即可



# 高级看板娘安装步骤

可换装、可拍照、可说话、可互动

## 1. fork 官方仓库

[live2d-widget](https://github.com/stevenjoezhang/live2d-widget)，目的是自定义修改，同时利用 github 的官方 cdn

## 2. 修改文件

- autoload.js：自动加载看板娘；
- waifu.css：看板娘样式；
- waifu-tips.js：看板娘说话的脚本；
- waifu-tips.json：看板娘说话的内容；

### 2.1 修改看板娘加载路径

修改 `autoload.js`

```
//注意：live2d_path参数应使用绝对路径
const live2d_path = "https://cdn.jsdelivr.net/gh/Mculover666/live2d-widget/";
```

> Mculover666 换成自己的 Github 用户名

### 2.2 修改看板娘布局和样式

修改 `waifu.css`

```css
#waifu {
	bottom: -1000px;
	right: 0;  // 看板娘位置
	line-height: 0;
	margin-bottom: -10px;
	position: fixed;
	transform: translateY(3px);
	transition: transform .3s ease-in-out, bottom 3s ease-in-out;
	z-index: 1;
}

#waifu-tool {
	color: #aaa;
	opacity: 0;
	position: absolute;
	left: 10px;  // 看板娘工具栏位置
	top: 70px;
	transition: opacity 1s;
}
```

### 2.3 提交到仓库

add commit push

### 2.4 发布新版本

由于使用了 Github 免费的 CDN 服务，所以还需要发布一个新的版本

![发布 releases ](https://cdn.myshenle.top/images/202305251741064.png)

## 3. 添加看板娘

Github上CDN的使用方式为
`https://cdn.jsdelivr.net/gh/你的用户名/你的仓库名@发布的版本号/文件路径`

修改主页文件，添加以下代码

```html
<script src="https://cdn.jsdelivr.net/gh/shenleg/live2d-widget@1.0.0/autoload.js"></script>
```

## 4. 复活看板娘

配置主题下的配置文件 `_config.yml` ，添加以下代码

```yaml
# ---------------------------------------------------------------
# 自定义看板娘
# ---------------------------------------------------------------
live2d:
  enable: true
```



# 参考

* [【Hexo搭建个人博客】（十二）Next主题中添加超级好玩的看板娘（CDN方式](https://blog.51cto.com/u_13640625/3032364)
