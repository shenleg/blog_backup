---
title: Windows-一次执行多条命令
categories:
  - 系统
  - Windows
tags:
  - win7
date: 2023-07-05 12:12:21
---





# 资源管理器显示我的电脑

![image-20230705121534668](https://cdn.myshenle.top/images/202307051215749.png)

![image-20230705122752192](http://cdn.myshenle.top/images/202307051227656.png)

参考：[WIN7下资源管理器默认打开我的电脑怎么搞_百度知道 (baidu.com)](https://zhidao.baidu.com/question/2126291250668167627.html)



# 资源管理器不显示库

1. win+r 运行 regedit
2. 到达：计算机\HKEY_CLASSES_ROOT\CLSID\{031E4825-7B94-4dc3-B131-E946B44C8DD5}\ShellFolder
3. 修改 Attributes 值
   * b090010d为删除库
   * b080010d为恢复库

参考：[Win7系统打开资源管理器后导航栏不显示库的解决方法 【百科全说】 (bkqs.com.cn)](https://www.bkqs.com.cn/content/0p8kx8gpz.html)