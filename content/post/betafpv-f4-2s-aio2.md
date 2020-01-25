+++
title = "Beta75 Pro 2 をRaspberry Pi Zero w で自律飛行"
date = 2020-01-25T13:00:00+09:00
categories = ["drone", "raspberrypi"]
description = ""
draft = false
image = "/images/20200113_191628.jpg"
tags = ["", ""]
author = ""
+++

# はじめに

前回投稿した[「PWM-SBUS CONVERTERを使用してBETAFPV F4 2S AIO BRUSHLESS NO RXをRASPBERRY PI ZERO Wから動作させてみる」](https://www.yokochi.jp/post/betafpv-f4-2s-aio/)の続きです。

今回は機体を作成して浮上するまでを作成しました



## 構成


parts   | name 
---------------|----------
  raspberry pi | raspberry pi zero w
  フライトコントローラ | BETAFPV F4 2S AIO Brushless No Rx
  距離センサ | VL53L0X
  ジャイロ加速度センサ | MPU-6050
  PWMドライバ | PCA9685 
 PWM SBUS Converter| S.BUS Turn PWM+s.bus 16CH Multifunctional Converter SBUS-PPM-PWM   
  モーター | BETAFPV 08028 12000KV Brushless Motor 

↓上側
{{< figure src="/images/20200113_191628.jpg" width="100%" >}}

↓下側
{{< figure src="/images/20200113_191645.jpg" width="100%" >}}


↓接続図
{{< figure src="/images/betafpv-f4.jpg" width="100%" >}}


## コード

- [GitHub上のコード](https://github.com/shigeru-yokochi/drone)を使用
- BETAFPV F4 2S AIO Brushless No Rx用の定義は以下の通り（aux2にarmを指定）

```
//BETAFPV F4 2S AIO Brushless No Rx
#define BETAFPV_F4_2S_AIO_THROTTLE	0
#define BETAFPV_F4_2S_AIO_ROLL		1
#define BETAFPV_F4_2S_AIO_PITCH		2
#define BETAFPV_F4_2S_AIO_YAW		3
#define BETAFPV_F4_2S_AIO_AUX2		4
#define BETAFPV_F4_2S_AIO_ARM		4	//aux2
#define BETAFPV_F4_2S_AIO_AUX3		5
#define BETAFPV_F4_2S_AIO_AUX4		6
#define BETAFPV_F4_2S_AIO_ARM_OFF	1000
#define BETAFPV_F4_2S_AIO_ARM_ON	1500
#define	BETAFPV_F4_2S_AIO_NEUTRAL			1519
#define	BETAFPV_F4_2S_AIO_NEUTRAL_THROTTLE	950
```


## 接続図

- コード変更を最小にするため既存と同じ構成にPWM-SBUS converterとフライトコントローラを接続
{{< figure src="/images/pwm-sbus.jpg" width="100%" >}}



## CleanFligthで動作確認
- armとThottleが想定通りの動作をしていることが波形で確認
- 距離センサ値と加速度センサ値は無視
{{< figure src="/images/BETAFPV-F4-2S-AIO-Brushless-No-Rx.jpg" width="100%" >}}

## 現物
{{< figure src="/images/20200104_113508.jpg" width="100%" >}}


## おわりに

- とりあえず確認できたので次は機体を作成してモータを回すところまでかな



<hr/>
# Amazon

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="https://rcm-fe.amazon-adsystem.com/e/cm?ref=qf_sp_asin_til&t=yokochi-22&m=amazon&o=9&p=8&l=as1&IS1=1&detail=1&asins=B07446WLQV&linkId=14f7f69e6e56594d6e5ca997465bcd74&bc1=ffffff&lt1=_top&fc1=333333&lc1=0066c0&bg1=ffffff&f=ifr">
    </iframe>

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="https://rcm-fe.amazon-adsystem.com/e/cm?ref=qf_sp_asin_til&t=yokochi-22&m=amazon&o=9&p=8&l=as1&IS1=1&detail=1&asins=B07Y4YYGY4&linkId=7910c9d3a1dfe381b2da2506c0cd90f2&bc1=ffffff&lt1=_top&fc1=333333&lc1=0066c0&bg1=ffffff&f=ifr">
    </iframe>

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="https://rcm-fe.amazon-adsystem.com/e/cm?ref=qf_sp_asin_til&t=yokochi-22&m=amazon&o=9&p=8&l=as1&IS1=1&detail=1&asins=B07WK1FRZG&linkId=9d2b0fde82d0951f97460bea050f6b55&bc1=ffffff&lt1=_top&fc1=333333&lc1=0066c0&bg1=ffffff&f=ifr">
    </iframe>

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="https://rcm-fe.amazon-adsystem.com/e/cm?ref=qf_sp_asin_til&t=yokochi-22&m=amazon&o=9&p=8&l=as1&IS1=1&detail=1&asins=B06Y2WW8DY&linkId=3e16c7029e5e16cc12396c0f717e928f&bc1=ffffff&lt1=_top&fc1=333333&lc1=0066c0&bg1=ffffff&f=ifr">
    </iframe>

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="https://rcm-fe.amazon-adsystem.com/e/cm?ref=qf_sp_asin_til&t=yokochi-22&m=amazon&o=9&p=8&l=as1&IS1=1&detail=1&asins=B07SLRG5J1&linkId=2a1d32f05d13cbb57c3403274afb7ccf&bc1=ffffff&lt1=_top&fc1=333333&lc1=0066c0&bg1=ffffff&f=ifr">
    </iframe>


<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="https://rcm-fe.amazon-adsystem.com/e/cm?ref=qf_sp_asin_til&t=yokochi-22&m=amazon&o=9&p=8&l=as1&IS1=1&detail=1&asins=B07PHSJ961&linkId=316ca88382339678525312c74a31400f&bc1=ffffff&lt1=_top&fc1=333333&lc1=0066c0&bg1=ffffff&f=ifr">
    </iframe>

<iframe style="width:120px;height:240px;" marginwidth="0" marginheight="0" scrolling="no" frameborder="0" src="https://rcm-fe.amazon-adsystem.com/e/cm?ref=qf_sp_asin_til&t=yokochi-22&m=amazon&o=9&p=8&l=as1&IS1=1&detail=1&asins=B07M87DLX5&linkId=7439403d3fc138c961db04dad6a9f85a&bc1=ffffff&lt1=_top&fc1=333333&lc1=0066c0&bg1=ffffff&f=ifr">
    </iframe>    


<hr/>
# Banggood


<a target='_blank' href='https://jp.banggood.com/S_BUS-Turn-PWMs_bus-14CH-Multi-functional-Converter-SBUS-to-PWM-p-984155.html?p=MD030313776065201709&custlinkid=749463'><img style="width:120px;" src='https://img.bgxcdn.com/images/2014/huangxiaobin/07/SKU243402/9850f4ea-9dfb-0e9c-c5f1-84f64caf9d32.jpg' alt='' >S.BUS PWM + s.bus 16CH多機能コンバータSBUS-PPM-PWM</a>

