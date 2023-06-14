---
title: Windows-PowerShell设置别名
categories:
  - 系统
  - Windows
tags:
  - 系统
  - Windows
date: 2023-06-14 17:13:54
---

# 需求

输入一长串命令非常繁琐，考虑简化命令输入，或者起别名。效果同 Linux 的 alias 设置别名。



# 步骤

## 1. 新建配置文件

查看配置文件位置

```powershell
> Get-Variable Profile

Name                           Value
----                           -----
PROFILE                        C:\Users\ZJ\Documents\PowerShell\Microsoft.PowerShell_profile.ps1
```

查看配置文件是否存在

```powershell
> Test-Path $profile
True
```

不存在则创建

```powershell
> New-Item -Type file -Force $profile

    Directory: C:\Users\ZJ\Documents\PowerShell

Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a---           2023/6/14    17:24              0 Microsoft.PowerShell_profile.ps1
```

## 2. 修改配置文件

把设置别名的命令放置在配置文件中，可以使修改永久生效

```
function Hexo-New { hexo new post }
function Hexo-Server { hexo clean && hexo g && hexo s --debug }
function Hexo-Deploy-Push { hexo clean && hexo g && hexo d && git add . && git commit -m "update" && git push }

Set-Alias hn Hexo-New
Set-Alias hs Hexo-Server
Set-Alias hdp Hexo-Deploy-Push
```

注意，只有带参数的命令才需要函数。已注册命令（包括绝对路径）直接 `Set-Alias`。支持引号。

## 3. 使配置生效

查看 PowerShell 默认执行策略

```powershell
> Get-ExecutionPolicy -List

        Scope ExecutionPolicy
        ----- ---------------
MachinePolicy       Undefined
   UserPolicy       Undefined
      Process       Undefined
  CurrentUser       Undefined
 LocalMachine       Undefined
```

修改 PowerShell 默认执行策略，默认在启动的时候，会以 Restricted 模式运行，此时不允许执行任何脚本

```powershell
> Set-Executionpolicy Remotesigned
```

重启 PowerShell



# 参考

* [Window 添加命令别名的方法 | Norwegian Wood](https://akynazh.site/posts/2022/06/how-to-add-command-alias-in-window/)
* [powershell创建永久别名_notepad设置别名](https://blog.csdn.net/weixin_34850743/article/details/100124969)
* [在Powershell中创建永久的别名alias](https://blog.csdn.net/u013391094/article/details/129340006)
* [使用别名 - PowerShell | Microsoft Learn](https://learn.microsoft.com/zh-cn/powershell/scripting/learn/shell/using-aliases?source=recommendations&view=powershell-7.3)
* [关于 Aliases - PowerShell | Microsoft Learn](https://learn.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_aliases?view=powershell-7.3)

