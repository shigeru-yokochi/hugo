+++
title = "ハイパーバイザーが実行されていないため、、、"
date = 2018-08-19T11:43:41+09:00
categories = ["IT", ""]
description = ""
draft = false
image = "/images/hyper-v.JPG"
tags = ["windows", "Docker","Hyper-V"]
author = ""
+++



Windows10 + Hyper-V + Dockerを構築する予定だったが、断念。。
理由はPCのCPUが古すぎでした。

# Doker起動時のエラー

![image](/images/docker.JPG)

# Hyper-Vから起動してみると以下のエラーが

![image](/images/hyper-v.JPG)

# systeminfoコマンドでハードウェアの互換性の検証の結果
第2レベルのアドレス変換が「いいえ」でした。
![image](/images/systeminfo.JPG)

# やはりSLATに対応していないようです。

![image](/images/coreinfo.JPG)



# 参考にしたサイト
https://docs.microsoft.com/ja-jp/virtualization/hyper-v-on-windows/reference/hyper-v-requirements

https://technet.microsoft.com/ja-jp/sysinternals/cc835722



- このCPUです

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="//rcm-fe.amazon-adsystem.com/e/cm?lt1=_blank&bc1=000000&IS2=1&bg1=FFFFFF&fc1=000000&lc1=0000FF&t=yokochi-22&language=ja_JP&o=9&p=8&l=as4&m=amazon&f=ifr&ref=as_ss_li_til&asins=B0012WDMNC&linkId=f09ab24be6fc0e3565b9e9ee7b79b9c3"></iframe>

