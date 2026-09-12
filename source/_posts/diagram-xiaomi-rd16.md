---
title: 小米 BE3600(黑色)的带宽分配
date: 2026-09-11 14:50:54
tags: 
  - 路由器
  - 拓扑图
index_img: 2026/diagram-xiaomi-rd16/diagram-xiaomi-rd16.png
---

# 基本信息

```yaml
CPU:
  型号: AN7563PT
  架构: 双核 ARM Cortex-A53
  主频: 1.0 GHz
内存: 256 MB DDR3L 1866
存储: 128 MB 
无线规格:
  2.4GHz频段:
    规格: Wi-Fi 7 2x2 MIMO
    最大频宽: 40 MHz
    理论最大速率: 688 Mbps
    FEM芯片: MT7976CN内置
  5GHz频段:
    规格: Wi-Fi 7 3x3 MIMO
    最大频宽: 160 MHz
    理论最大速率: 2882 Mbps
    FEM芯片: MT7976CN内置
接口:
  以太网口:
    - 1 Gbps * 4
电源:
  输入: 12V / 1A
```
注：
* AIROHA AN7563PT这款CPU找不到公开的手册，基本信息是根据宣传资料填入的。
* 射频芯片MT7976CN在5Ghz上是3T3R，但是数据流SS仍然只有2，多出来的一根天线应该是类似Filogic Xtra Range技术。官网上的描述来看该技术是用于增加连接范围。

# 带宽图解

{% asset_img diagram-xiaomi-rd16.png %}

注：
* MT7990AN和AN7563PT之间是通过PCIe 2.0 x1连接推测的依据是使用MT7990AN做的无线网卡是这个规格。

# 其它


用着小米BE3600这名字一共有外形一致的三款型号，分别是：
 * 黑色外壳，型号名RD16，只有千兆网口，使用联发科子公司达发的AN7563PT。本文则是这款。
 * 白色外壳，型号名RD15，有一个2.5G网口，使用高通IPQ5312处理器。它的带宽分配见[这里](/2026/diagram-xiaomi-rd16/)。
 * 白色外壳，型号名RD16，只有千兆网口，找不到拆解，推测也是使用高通IPQ5312处理器。

# 参考链接

1. 三款小米BE3600的官网：
   * 白色2.5G款：[Xiaomi路由器BE3600](https://www.mi.com/xiaomi-routers/be-3600)
   * 白色全千兆款：[Xiaomi路由器 BE3600立即购买-小米商城](https://www.mi.com/shop/buy/detail?product_id=19845)
   * 黑色全千兆款：[Xiaomi路由器BE3600(黑色）立即购买-小米商城](https://www.mi.com/shop/buy/detail?product_id=21494)
   * 两款全千兆款官网上都只有商场购买链接，感觉未来很有可能就打不开了......
2. MT7990AN做的MiniPCIe无限网卡：[AW7990-NPD 802.11ax Wi-Fi 6 MT7990 Mini PCIe Wireless Card](asiarf.com/product/wifi-7-be3600-mini-pcie-ap-module-aw7990-npd)
3. MT7976CN的技术手册：[MT7976CN Datasheet](https://datasheet4u.com/download/1603034/MT7976CN.html)