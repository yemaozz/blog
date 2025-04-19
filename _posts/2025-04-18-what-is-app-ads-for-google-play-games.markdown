---
title: 小游戏出海谷歌之什么是app-ads
layout: post
date: '2025-04-18 10:00:10'
categories:
- 小游戏出海
- 谷歌play
---

什么是app-ads.txt？官方解释如下

应用授权卖方（或 app-ads.txt）是一项 IAB Tech Lab 计划，有助于确保只通过您认定的授权渠道销售您的应用广告资源。通过创建 app-ads.txt 文件，您可以更好地掌控哪些卖方有权销售您应用内的广告空间，并可防止向广告客户展示仿冒广告资源。app-ads.txt 文件是公开的，可供广告交易平台、供应方平台 (SSP) 以及其他买方和第三方供应商抓取。应用授权卖方 (app-ads.txt) 是授权数字卖方 (ads.txt) 计划的延伸和扩展，后者最初设计用于保护网络广告资源。app-ads.txt 在 ads.txt 的基础上扩展了兼容性，使之支持移动应用中展示的广告。为避免损失大量广告收入，您需要实施 app-ads.txt 文件。

比较拗口，通俗点解释。我的理解是，IAB Tech Lab 计划给各家广告平台分配了一个id，我们开发者从各广告平台获得对应的id，并通过商店官网公开展示给所有人查看以证明我们经过合法授权。初次接触者如果不理解也没关系，接着往下我们照着做。

没添加有什么影响？

我个人碰到过的实际案例，unity ads，没添加前收入只有0.0几美元，添加后收入变成几美元。不过谷歌admob没有感受到影响，收入基本一致。但不论如何，这项工作完善了才能心安。

如何添加？

app-ads.txt就是一个txt文件，在电脑上新建一个txt，重命名为app-ads.txt，之后往该txt文件里添加内容，内容格式一般如下

```
#
AdMob
#
google.com, pub-6716225838534735, RESELLER, f08c47fec0942fa0
#
Applovin
#
applovin.com, 842af0f98ced43638c9bfa1e8293f364, DIRECT
loopme.com, 11303, RESELLER, 6c8d5f95897a5a3b
pubmatic.com, 158862, RESELLER, 5d62403b186f2ace
#
Mintegral
#
adwmg.com, 100962, DIRECT, c9688a22012618e7
google.com, pub-8309773808661346, RESELLER, f08c47fec0942fa0
google.com, pub-8622186303703569, DIRECT, f08c47fec0942fa0
#
UnityAds
#
risecodes.com, 6486c6155b231000010244b0, RESELLER
admixer.net, 4ca083cd-412f-49fe-b832-5b66ee490d9a, RESELLER
algorix.co, 54616, RESELLER
#
IronSource
#
risecodes.com, 66fab6981efdb80001a3dadc, RESELLER
ironsrc.com, 189107, DIRECT, 79929e88b2ba73bc
adbility-media.com, 187, RESELLER
#
Pangle
#
pangleglobal.com, 4319, DIRECT
pubmatic.com, 161490, RESELLER, 5d62403b186f2ace
#
Meta
#
facebook.com, 838871949512065, RESELLER, c3e20eee3f780d68
facebook.com, 199171815742149, RESELLER, c3e20eee3f780d68
```

![]({{ "/assets/images/2025-04-18/1.webp" | relative_url }})

在哪找app-ads?

admob，如下图，在admob后台，应用-所有应用-app-ads，就能找到，直接复制。

![]({{ "/assets/images/2025-04-18/2.webp" | relative_url }})

applovin，在后台左侧栏找到Account→App-ads

unity ads，在后台左侧栏找到Unity Ads Monetization→organization setting→App-ads.txt，如果是中文版本Unity Ads Monetization→组织设置→App-ads.txt。

mintegral，在后台顶部找到应用设置→APP-ads

Facebook，在后台找到集成→资产→创建资产→创建广告位过程中就能找到。或者在浏览器地址栏中找到business_id=后面有一串数字id，将这串数字id替换进如下格式中即可。

```
facebook.com, business_id, DIRECT, c3e20eee3f780d68
```

ironsource，比较特殊，需要咨询对方的联系人才能获取。

pangle，在后台找到账号id，替换掉如下“Account ID”即可。行2部分固定。

```
pangleglobal.com, Account ID, DIRECTpubmatic.com, 161490, RESELLER, 5d62403b186f2ace
```

txt文件的内容都填充完了，这个时候需要将app-ads.txt文件上传网站的根目录下。

![]({{ "/assets/images/2025-04-18/3.webp" | relative_url }})

还需要搭建网站，是不是很麻烦？而且域名要钱，服务器要钱，都是成本。对此确实如此，所以我们要找地方托管我们的网站，关于网站托管，将单开文章介绍。

End