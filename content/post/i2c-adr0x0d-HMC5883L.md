+++
title = "i2cアドレスが0x0dのHMC5883L"
date = 2017-04-05T18:43:41+09:00
categories = ["drone", ""]
description = ""
draft = false
image = "/images/ng-HMC5883L.jpg"
tags = ["", ""]
author = ""
+++

# 内容

手元にあるHMC588Lモジュール(3軸デジタルコンパス)が全く動作しない。
違う石を実装しているようだ。
結構出回っていると思うので、もし入手してしまった場合は本記事を参考にして頂ければ思い投稿します。

この記事の通りだった↓

https://www.raspberrypi.org/forums/viewtopic.php?t=172244&p=1102197

# 対策

別のモジュールを用意して動作確認をしました。

その記事はこちらです↓
[3軸デジタルコンパスHMC5883Lを使ってみる](http://qiita.com/shigeru-yokochi/items/c36c975e14c0c86886c0)


# 動作しないHMC5883Lの見分け方

## ICの刻印

- 誤：DA 5883 6012　
- 正：L883 2230

{{< figure src="https://qiita-image-store.s3.amazonaws.com/0/146154/5e4bcc28-9359-cd56-2f7c-a249eefcaf01.jpeg" width="100%" >}}


## i2cアドレス

- 誤：0x0d
- 正：0x1e

{{< figure src="https://qiita-image-store.s3.amazonaws.com/0/146154/4757c922-5e42-5812-e75c-6187ecd1713f.png" width="100%" >}}


（裏側参考）↓
{{< figure src="https://qiita-image-store.s3.amazonaws.com/0/146154/3c179d40-cf23-d08e-b239-8e39895755f2.jpeg" width="100%" >}}



