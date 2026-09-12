---
title: 小米 BE3600 2.5G版的带宽分配
date: 2026-09-11 14:50:44
tags: 
  - 路由器
  - 拓扑图
index_img: 2026/diagram-xiaomi-rd15/diagram-xiaomi-rd15.png
---

# 基本信息

```yaml
CPU:
  型号: IPQ5312
  架构: 四核 ARM Cortex A53
  主频: 1.1 GHz
内存: 256 MB DDR3L 1866
存储: 128 MB 
无线规格:
  2.4GHz频段:
    规格: Wi-Fi 7 2x2 MIMO
    最大频宽: 40 MHz
    理论最大速率: 688 Mbps
    FEM芯片: KCT8245SD
  5GHz频段:
    规格: Wi-Fi 7 2x2 MIMO
    最大频宽: 160 MHz
    理论最大速率: 2882 Mbps
    FEM芯片: KCT8576HE
接口:
  以太网口:
    - 2.5 Gbps * 1
    - 1 Gbps * 3
电源:
  输入: 
    - 12V / 1.5A
    - 12V / 1.25A
```

# 带宽图解

{% asset_img diagram-xiaomi-rd15.png %}


# 其它

1. IPQ5312的手册没有公开，四核A53@1.1Ghz在宣传物料上可以印证。
2. 用着小米BE3600这名字一共有外形一致的三款型号，分别是：
   * 白色外壳，型号名RD15，有一个2.5G网口，使用高通IPQ5312处理器。本文的2.5G款。
   * 白色外壳，型号名RD16，只有千兆网口，找不到拆解，推测也是使用高通IPQ5312处理器。
   * 黑色外壳，型号名RD16，只有千兆网口，使用联发科子公司达发的AN7563PT。它的带宽分配见[这里](/2026/diagram-xiaomi-rd16/)。
   * 白色外壳全千兆的版本虽然找不到拆解，但官网上没有专门对应的ROM下载链接，从这方面来看它应该是和2.5G款有近乎完全一致的设计。
3. 根据参考链接，该款似乎后期替换出了轻微缩水的版本：电源适配器从12V 1.5A缩水成12V 1.25A（不过仍然完全够用）；主板少了两颗电容和几个芯片背部的屏蔽片；散热板重新设计过，稍微短一些和窄一些。高通全千兆款在小米商城的评价里也能找到1.25V的版本，但是拆解就找不到了。

# 参考链接

1. 三款小米BE3600的官网：
   * 白色2.5G款：[Xiaomi路由器BE3600](https://www.mi.com/xiaomi-routers/be-3600)
   * 白色全千兆款：[Xiaomi路由器 BE3600立即购买-小米商城](https://www.mi.com/shop/buy/detail?product_id=19845)
   * 黑色全千兆款：[Xiaomi路由器BE3600(黑色）立即购买-小米商城](https://www.mi.com/shop/buy/detail?product_id=21494)
   * 两款全千兆款官网上都只有商场购买链接，感觉未来很有可能就打不开了......
2. 拆机：[小米BE3600无线路由器拆机](https://www.acwifi.net/26827.html)
3. 缩水版拆机：[小米BE3600拆机1.25A版本白色](https://www.acwifi.net/34321.html)
4. 带宽推测依据：[Qualcomm/IPQ6000 - WikiDevi.Wi-Cat.RU](https://wikidevi.wi-cat.ru/Qualcomm/IPQ6000)
5. 交换机芯片手册：[YT9215S Datasheet Download](https://datasheet4u.com/download/1604366/YT9215S.html)
   * 这款芯片看手册的话，其实还能再额外引出两个千兆网口和一个2.5G网口。
