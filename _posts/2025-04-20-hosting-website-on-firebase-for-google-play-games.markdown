---
title: 小游戏出海谷歌之网站托管在firebase host
layout: post
date: '2025-04-20 10:00:10'
categories:
- 小游戏出海
- 谷歌play
---

小游戏上线谷歌play需要app-ads.txt文件，需要官网，对于刚开始尝试谷歌play的开发者来说，域名+服务器的成本也是一项支出，那么海外一些免费托管工具就可以用起来。这里介绍下firebase host的方案，该方案属于100%免费，不过折腾起来需要费些时间。

此处先概述下流程，后面将详细介绍

1. 官方教程 https://firebase.google.com/docs/cli
2. 首先安装firebase tools。可以通过npm安装，Linux如果翻墙问题可以查看官方教程用curl安装
3. 在终端登录谷歌账号
4. 推送文件到hosting

## 后续更新推送指令

```
#更新Firebase指令（Linux）
curl -sL firebase.tools | upgrade=true bash
#退出登录指令
firebase logout
#windows代理指令#
set http_proxy=http://127.0.0.1:7890
#Linux代理指令#
export http_proxy=http://127.0.0.1:7890
export https_proxy=http://127.0.0.1:7890
#重新登录指令
firebase login --no-localhost
#推送
firebase deploy --only hosting
```

## 创建项目

首页谷歌账号登录 https://firebase.google.com/?hl=zh-cn

![]({{ "/assets/images/2025-04-20/1.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/2.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/3.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/4.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/5.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/6.webp" | relative_url }})

到此处，项目创建完毕，打开终端或者cmd安装firebase tools

## 安装firebase tools

### Windows

对于Windows系统，Windows+R→输入cmd或者开始按钮中找w开头Windows powershell→弹出来的窗口中输入指令

```
npm install -g firebase-tools
```

如果没有npm，需要安装nodejs

1. 在 Node.js 官方网站 https://nodejs.org/en/ 下载最新版本的 Node.js 安装包，建议选择LTS版本（长期支持版）。
2. 双击下载的 .msi 安装程序，按照提示进行安装。
3. 在运行安装程序时的“Custom Setup”界面上，确保包含 “Add to PATH” 选项是被选中的。这将让 Node.js 自动添加到您的系统 PATH 环境变量中，这样您在终端中输入 node 命令时，就可以随时启动 Node.js。
4. 等待安装完成，然后重新启动您的命令行终端。

在 macOS 或 Linux 上安装 Node.js，可以按照官方网站上的安装说明，或者使用包管理器来安装 Node.js。在终端中输入以下命令即可：

### macOS

```
$ brew install node
```

### Ubuntu / Debian

```
$ sudo apt-get install nodejs
```

### Fedora / Red Hat Enterprise Linux / CentOS

```
$ sudo yum install -y nodejs
```

需要注意的是，如果使用的是 macOS 或 Linux 系统，可能不需要手动将 Node.js 添加到系统 PATH 环境变量中。在大多数情况下，Node.js 包管理器会自动执行这项任务。

安装好之后重新运行，这一步的目的是安装firebase-tools这个工具

```
npm install -g firebase-tools
```

终端长这样

![]({{ "/assets/images/2025-04-20/7.webp" | relative_url }})

或者这样

![]({{ "/assets/images/2025-04-20/8.webp" | relative_url }})

### Linux

Linux安装firebase tools推荐使用curl。如下，--proxy是通过代理下载。详细参见官方教程

```
curl --proxy 127.0.0.1:7890 -sL https://firebase.tools | bash
```

## 登录谷歌账号及推送文件

安装成功后，在本地新建一个文件夹，尽量不要用中文名称，例如下图

![]({{ "/assets/images/2025-04-20/9.webp" | relative_url }})

然后复制路径

![]({{ "/assets/images/2025-04-20/10.webp" | relative_url }})

在终端里输入

```
cd D:\build\miaoteagame
```

![]({{ "/assets/images/2025-04-20/11.webp" | relative_url }})

如下图1，这个时候没有跳到路径D:\\build\\miaoteagame，需要再输入D:然后回车即可，如下图2

![]({{ "/assets/images/2025-04-20/12.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/13.webp" | relative_url }})

然后开始登录firebase

登录前先设置代理，代理IP、端口根据实际情况填写，如果使用的clash，那就是127.0.0.1：端口

```
#windows#
set http_proxy=http://127.0.0.1:7890
#Linux#
export http_proxy=http://127.0.0.1:7890
export https_proxy=http://127.0.0.1:7890
```

![]({{ "/assets/images/2025-04-20/14.webp" | relative_url }})

开始登录

```
firebase login --no-localhost
```

如下图这个状态是已经登录成功。首次登录按上面代码输入后回车，会出现一个链接，复制链接到浏览器打开，然后根据提示一步步操作。Linux可能会出现验证失败的提示，检查前后空格。

![]({{ "/assets/images/2025-04-20/15.webp" | relative_url }})

登录成功后对项目进行初始化

```
firebase init
```

输入Y回车

![]({{ "/assets/images/2025-04-20/16.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/17.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/18.webp" | relative_url }})

有时候会出错，大概率是网络问题，直接重试即可

![]({{ "/assets/images/2025-04-20/19.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/20.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/21.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/22.webp" | relative_url }})

![]({{ "/assets/images/2025-04-20/23.webp" | relative_url }})

最后，将文件复制到public目录下覆盖，用如下指令上传到firebase托管

```
firebase deploy --only hosting
```

![]({{ "/assets/images/2025-04-20/24.webp" | relative_url }})

成功后如下图所示，firebase的默认样式

![]({{ "/assets/images/2025-04-20/25.webp" | relative_url }})

接着把网站和app-ads.txt复制到public文件夹中，用指令deploy上传即可完成托管

![]({{ "/assets/images/2025-04-20/26.webp" | relative_url }})

如果需要自定义域名，可以继续如下操作。不过我个人建议这个成本也可以省下来。

![]({{ "/assets/images/2025-04-20/27.webp" | relative_url }})

firebase需要域名所有权的验证，如下图，是阿里云的验证

![]({{ "/assets/images/2025-04-20/28.webp" | relative_url }})

End