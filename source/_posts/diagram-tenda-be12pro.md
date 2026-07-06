---
title: 腾达 BE7200 （BE12 Pro）的带宽分配
date: 2026-07-06 18:56:01
tags: 
  - 路由器
  - 拓扑图
---

# 带宽图解

{% asset_img diagram-tenda-be12pro.png %}

注：
* 虽然内存上的丝印有xxx**256**xxx的字样，但实际上它是一颗**512MB**的内存颗粒。

# 基本信息

```yaml
CPU:
  型号: MT7987A (MediaTek Filogic 850)
  架构: 四核 ARM Cortex-A53
  主频: 2.0 GHz
内存: 512 MB DDR3 2133MHz
存储: 128 MB SPI Flash
无线规格:
  2.4GHz频段:
    规格: Wi-Fi 7 4x4 MIMO
    最大频宽: 40 MHz
    理论最大速率: 1376 Mbps
    FEM芯片: MT7975N内置
  5GHz频段:
    规格: Wi-Fi 7 4x4 MIMO
    最大频宽: 160 MHz
    理论最大速率: 5765 Mbps
    FEM芯片: MT7979N内置
  总无线速率: BE7200
接口:
  以太网口:
    - 2.5 Gbps * 2
    - 1 Gbps * 3
电源:
  输入: 12V / 2A
```
注：
* 5Ghz芯片MT7979N硬件上是4T5R，多出来的一根天线是用于Filogic Xtra Range技术。官网上的描述来看该技术是用于增加连接范围，应该不实际增加带宽。

# 参考链接

1. 官网：[BE12 Pro BE7200双频千兆Wi-Fi 7路由器 - 腾达(Tenda) 腾达中文网站](https://www.tenda.com.cn/product/BE12Pro)
   1. 宣传图中声称5Ghz支持5收5发是错误的，见前文基本信息的注解。
2. 拆解：[MT7987A+BE7200不到300元，可能是刷机圣体 | 腾达be7200双频wifi7路由器](https://www.zhihu.com/tardis/zm/art/2000981694761694012)
3. MT7987A的规格表：[香蕉派 BPI-R4 Lite Wifi 7 开源路由器开发板采用联发科MT7987芯片方案 | BananaPi Docs](https://docs.banana-pi.org/zh/BPI-R4_Lite/BananaPi_BPI-R4_Lite)