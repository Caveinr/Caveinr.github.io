---
title: TP-Link 7DR3610易展版的带宽分配
date: 2026-09-14 16:12:52
tags: 
  - 路由器
  - 拓扑图
index_img: 2026/diagram-tplink-7dr3610/diagram-tplink-7dr3610.png
---

# 基本信息

```yaml
CPU:
  型号: AN7563PT
  架构: 双核 ARM Cortex-A53
  主频: 1.0 GHz
内存: 512 MB DDR3 1866
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
  输入: 
    - 12V / 1A
```

注：
* AIROHA AN7563PT这款CPU找不到公开的手册，基本信息是根据宣传资料填入的。
* 射频芯片MT7976CN在5Ghz上是3T3R，但是数据流SS仍然只有2。多出来的一根天线应该是类似Filogic Xtra Range技术，用于增加连接范围。

# 带宽图解

{% asset_img diagram-tplink-7dr3610.png %}

注：
* MT7991B和AN7563PT之间是通过PCIe 2.0 x1连接是参考其它同处理器的连接情况推测的。不过需要一提的是在用MT7991A的BE5100方案上有开发板的原理图上是使用的PCIe 2.0 x2连接的。

# 参考链接

1. 官网：[TL-7DR3610易展版 BE3600双频Wi-Fi 7无线路由器 - TP-LINK官方网站](https://www.tp-link.com.cn/product_3288.html)
2. 拆机：[TP-LINK BE3600 7DR3610拆机](https://www.acwifi.net/26793.html)
3. 内存颗粒数据手册：[A3T4GF40BBF-HP | Datasheet | Zentel | LCSC Electronics](https://www.lcsc.com/datasheet/C491349.pdf)
