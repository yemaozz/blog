---
title: 小游戏出海谷歌之广告变现
layout: post
date: '2025-04-15 10:00:10'
categories:
- 小游戏出海
- 谷歌play
---

在选择使用哪几家广告变现之前，先搞清楚几个概念。

## 什么是广告聚合？

广告聚合平台将对多个广告渠道的访问集中到一个 SDK 集成，利用优化算法来确定可以为应用开发者提供合适广告位且产生最高 CPM 的广告渠道。

## 为什么使用广告聚合？

广告聚合平台可以确定各种广告来源的 CPM，并为产生最高 CPM 的广告来源提供展示机会，正是这种竞争推高了 CPM，从而提高我们的广告收入。

## 广告聚合平台怎么选？

海外广告聚合平台有applovin、admob、ironsource、topon等，其实都是很成熟的聚合平台了，如果对哪家更加熟悉，则可以优先选择，否则大同小异，不必太过纠结。小编现在使用的是applovin。

## 广告变现渠道怎么选？

海外广告变现渠道有非常非常多，AppLovin，Amazon Publisher Services，BidMachine，BIGO Ads，Chartboost，DT Exchange，Google Bidding，InMobi，IronSource，Liftoff Monetize，Meta，Mintegral，MobileFuse，Moloco，Ogury，PubMatic，Pangle，Smaato，Unity，Verve Group，VK Ad Network，Yandex，YSO Network等。通过广告聚合平台是能够相对比较快的将变现渠道接入，那是不是接入越多，cpm越高了？理论上是，实际上得不偿失。因为大部分变现渠道都需要达到100美金以上后才能提现，当我们的游戏用户量不大的时候，则大部分收入还是会集中在头部变现平台，底部变现平台有可能几年都不一定能提现一次，如此这部分收入则基本浪费掉。以及接入越多变现平台，游戏包体也会越大，对买量转化也会有一定的负面影响。再者接入越多变现平台sdk，会碰到更多莫名的报错，小变现平台的报错也会找不到网上分享的解决方案。因此，对于刚开始测试游戏，不需要接入太多。

小编这边经过这几年的摸索，目前方案为applovin聚合+admob/unity/mintegral/Facebook/ironsource/pangle（即国内字节的穿山甲），下图为小编这边的一个收入排行，按顺序分别为admob、applovin、unity、mintegral、Facebook、pangle、ironsource、DT Exchange（已放弃，需要到1000美元才能提现）。

![]({{ "/assets/images/2025-04-15/1.webp" | relative_url }})

## 变现平台注册

| 变现平台 | 注册主体 | 收款 | 备注 |
|---|---|---|---|
| 谷歌admob | 个人或公司 | 电汇 | 小编都直接跟随谷歌play开发者账号，不过重点需要解决pin码问题，将新开文章介绍 |
| applovin | 公司 | 电汇 | 注册时候需要填写公司，不过可以随便填下，不需要认证 |
| Facebook | 个人或公司 | 电汇 | 2024年后Facebook全面退出大陆地区，大陆地区的银行卡无法收款，所以如果没有境外主体，建议放弃 |
| mintegral | 个人或公司 | 个人户-支付宝公司户-电汇 | 为国内公司，收款直接接收人民币。如果是公司主体需要开发票。个人户收款不涉及个人所得税。收款确实方便，不过实际入账被扣的手续费最高。且注册后需要联系对方客户经理确认。 |
| pangle | 公司 | 电汇 | 注册需要公司，且需要营业执照认证，建议先放弃 |
| ironsource | 公司 | 电汇 | 注册时候需要填写公司，不过可以随便填下，不需要认证 |
| unity | 个人或公司 | 电汇 | 对于unity开发，unity账号直接使用即可 |

电汇收款就是我们的银行卡，如果个人，建议使用中农工建四大行，以工行为例，工行app→搜索“跨境汇款”→小字“查询收汇信息”→复制收款信息。一般有这几个信息：收款账号、收款人名称、swift码、银行分行、银行地址。（小声比比，swift就是老美用来制裁毛熊的金融核弹）。

电汇收款也可以使用第三方收款，比如珊瑚跨境（coralglobal）、万里汇（阿里家的）、pingpong等。此处不赘述，将新开文章详细介绍。注册后就可以创建一个收款账号，会有收款账号、收款人名称、swift码、银行分行、银行地址等信息，成功收款后钱就会入账到这些第三方平台，之后我们可以自己去提现，第三方平台收取0.5%-1%的服务费。

对于个人没有公司的情况，建议前期applovin+admob/unity/mintegral

至少applovin+admob，谷歌在广告变现的地位无可撼动，如果缺了admob很可能产品永远都无法买正。如果后面产品量级逐渐变大，比如DAU达到1000+，建议还是将以上几家变现平台都接入。

注册方法，搜索找到官网，直接一步步注册即可，另外这些变现平台的注册经常都需要一个官网，建议先通过谷歌play过审一款app（未接入广告的app）再去注册，将app的商店链接作为官网地址。

## 税表

注册后一般还需要填写一个税表（平台公司注册地在老美的一般都需要，pangle和mintegral不用，前者注册地新加坡，后者国内）。老美有各种税表，1040、1099、W-2/4/9/8BEN等等，太复杂，我们不需要深究，只关注W-8BEN即可。W-8BEN表是外国个人或公司用来证明自己是非美国税务居民的文件。该税表看着挺复杂，但核心内容就是一点“我不是美国居民，我不生活在美国，不享受美国税率优惠”，下面以applovin的公司税表填写为例截图，个人也是类似，其他平台也是类似。

![]({{ "/assets/images/2025-04-15/2.webp" | relative_url }})

![]({{ "/assets/images/2025-04-15/3.webp" | relative_url }})

![]({{ "/assets/images/2025-04-15/4.webp" | relative_url }})

![]({{ "/assets/images/2025-04-15/5.webp" | relative_url }})

![]({{ "/assets/images/2025-04-15/6.webp" | relative_url }})

（至于近期加关税有没有影响，也不懂了，没法深究）

下面是机器翻译版本

![]({{ "/assets/images/2025-04-15/7.webp" | relative_url }})

![]({{ "/assets/images/2025-04-15/8.webp" | relative_url }})

![]({{ "/assets/images/2025-04-15/9.webp" | relative_url }})

![]({{ "/assets/images/2025-04-15/10.webp" | relative_url }})

![]({{ "/assets/images/2025-04-15/11.webp" | relative_url }})

都完成后，就可以开始创建广告位，接入sdk，此文先不赘述。

End