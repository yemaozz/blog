---
title: 小游戏出海谷歌之网站托管在GitHub Pages
layout: post
date: '2025-04-19 10:00:10'
categories:
- 小游戏出海
- 谷歌play
---

小游戏上线谷歌play需要app-ads.txt文件，需要官网，对于刚开始尝试谷歌play的开发者来说，域名+服务器的成本也是一项支出，那么海外一些免费托管工具就可以用起来。这里介绍下GitHub Pages的方案，该方案需要购买域名，我一般选择.top域名，一年20人民币左右。查找资料发现类似GitHub Pages的服务还有，国外GitLab Pages、Netlify、Vercel、Cloudflare Pages、Render；国内Gitee Pages（码云）、Coding Pages（腾讯云开发者平台），不过国内应该都需要域名备案。我个人只使用过GitHub Pages，本文将重点介绍。此处先概述下流程，后面将详细介绍

1. 注册GitHub账号，电脑上安装git
2. 创建项目，克隆到本地
3. 创建index文件和app-ads.txt文件，上传
4. 自定义域名，解析域名
5. 检查确认

## 什么是Git、GitHub、GitHub Pages？

- **Git**：Git是一个分布式版本控制系统。
- **GitHub**：GitHub是一个在线软件源代码托管服务平台，用于公开程序或软件的代码，使用Git作为版本控制软件。
- **GitHub Pages**：GitHub Pages是一项静态站点托管服务，它直接从GitHub上的存储库获取HTML、CSS 和JavaScript文件，（可选）通过构建过程运行文件，然后发布网站。

如果对这些完全没概念的网友，可以再找资料理解下。

## 注册GitHub账号

打开github.com，找到注册，使用邮箱注册即可。

## 安装Git

搜索Git（记得避开广告），官网域名git-scm.com，找到最新版本下载，下载完成后正常安装软件。

## 创建项目

注册好GitHub账号后，如下图，点击创建存储库

![]({{ "/assets/images/2025-04-19/1.webp" | relative_url }})

![]({{ "/assets/images/2025-04-19/2.webp" | relative_url }})

创建后就来到如下界面，这里我们先介绍下直接上传文件的方式，不通过指令。不过如果长期维护还是建议使用指令，文章后面我们会再简单介绍通过指令同步云端和本地的方式。如下图，记住Add files→Upload files。

![]({{ "/assets/images/2025-04-19/3.webp" | relative_url }})

## 创建index文件和app-ads.txt文件

不会写代码？让deepseek帮忙写一个（deepseek表示这太简单了）。

![]({{ "/assets/images/2025-04-19/4.webp" | relative_url }})

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello Page</title>
    <style>
        body {
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
        }
        h1 {
            font-size: 3rem;
        }
    </style>
</head>
<body>
    <h1>hello</h1>
</body>
</html>
```

在本地新建一个txt文件，命名为index.txt，复制以上代码到txt文件中，保存并重命名为index.html。重命名后，直接双击运行确认下（一个简单的展示，一般不会出问题）。接着创建app-ads.txt（如果不需要app-ads.txt就可以无视这步）。在本地新建一个txt文件，命名为app-ads.txt。复制各广告变现平台的app-ads到txt文件中，保存。如下图

![]({{ "/assets/images/2025-04-19/5.webp" | relative_url }})

上传index.html和app-ads.txt到GitHub中。打开前面创建的项目，找到Add files→Upload files

![]({{ "/assets/images/2025-04-19/6.webp" | relative_url }})

![]({{ "/assets/images/2025-04-19/7.webp" | relative_url }})

上传完成看到如下图两个文件都在了

![]({{ "/assets/images/2025-04-19/8.webp" | relative_url }})

## 设置GitHub Pages

上传完成，就是把文件放到仓库里了，接着要设置成可以对外展示，就需要设置GitHub Pages

![]({{ "/assets/images/2025-04-19/9.webp" | relative_url }})

![]({{ "/assets/images/2025-04-19/10.webp" | relative_url }})

如上保存后会看到下图样式，此时需要等待几分钟

![]({{ "/assets/images/2025-04-19/11.webp" | relative_url }})

刷新几次页面后应该就能看到如下图

![]({{ "/assets/images/2025-04-19/12.webp" | relative_url }})

访问网站确认下，成功

![]({{ "/assets/images/2025-04-19/13.webp" | relative_url }})

访问app-ads.txt确认下，成功

![]({{ "/assets/images/2025-04-19/14.webp" | relative_url }})

app-ads文件官方要求需要放在根目录下，不使用自定义域名的情况下只能在二级目录下。因此接下来我们需要设置下自定义域名。

![]({{ "/assets/images/2025-04-19/15.webp" | relative_url }})

这里以阿里云域名解析为例，将指定域名解析到GitHub

![]({{ "/assets/images/2025-04-19/16.webp" | relative_url }})

![]({{ "/assets/images/2025-04-19/17.webp" | relative_url }})

![]({{ "/assets/images/2025-04-19/18.webp" | relative_url }})

以上都设置后，可能需要等待几分钟同步

![]({{ "/assets/images/2025-04-19/19.webp" | relative_url }})

访问确认，首页和app-ads.txt都ok。到此就设置完成了，至于网站要美化则只能各显神通了。

![]({{ "/assets/images/2025-04-19/20.webp" | relative_url }})

![]({{ "/assets/images/2025-04-19/21.webp" | relative_url }})

## Git指令

把项目克隆到本地

在文章前面有说到安装Git，安装成功的话，在空白处右键就能看到如下图，打开Git Bash

![]({{ "/assets/images/2025-04-19/22.webp" | relative_url }})

回到项目地址，复制项目地址

![]({{ "/assets/images/2025-04-19/23.webp" | relative_url }})

在打开的Git Bash里输入指令

```
git clone 复制的URL
```

![]({{ "/assets/images/2025-04-19/24.webp" | relative_url }})

如上图运行结果，就是成功同步到了本地。如果是首次运行，可能会有未登录的报错，则需要按以下指令登录，此处只简单带过，详细的可以通过deepseek等ai工具搜索，能找到很详细的介绍。

```
git config --global user.email "you@example.com"
git config --global user.name "Your Name"
```

克隆到本地后，我们还需要知道修改后怎么提交。以下三条指令运行后即可将修改内容提交到GitHub仓库。

```
git add .
git commit -m "自定义说明"
git push
```

![]({{ "/assets/images/2025-04-19/25.webp" | relative_url }})

到此网站托管都完成。

End