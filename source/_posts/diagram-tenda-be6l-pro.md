---
title:  腾达云霄BE5100 （BE6L Pro）的带宽分配
date: 2026-09-16 12:20:56
tags: 
  - 路由器
  - 拓扑图
index_img: 2026/diagram-tenda-be6l-pro/diagram-tenda-be6l-pro.png
---

# 基本信息

```yaml
CPU:
  型号: AN7563PT
  架构: 双核 ARM Cortex-A53
  主频: 1.0 GHz
内存: 512 MB DDR3L 1866
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
    理论最大速率: 4323 Mbps
    FEM芯片: MT7976CN内置
接口:
  以太网口:
    - 2.5Gbps * 1
    - 1 Gbps * 3
电源:
  输入: 
    - 12V / 1.5A
```

注：
* AIROHA AN7563PT这款CPU找不到公开的手册，基本信息是根据宣传资料填入的。

# 带宽图解

{% asset_img diagram-tenda-be6l-pro.png %}

注：
* MT7991A和AN7563PT之间是通过PCIe 2.0 x2连接是参考某开发板的原理图推测的，不过理论上PCIe 3.0 x1带宽也同样足够，对此也不是很确定。
* 内存颗粒兼容DDR3和DDR3L两种电压。参考其它同CPU型号的机型这里应该是工作在DDR3的电压下。

# 参考链接

1. 官网：[BE6L Pro BE5100双频2.5G口Wi-Fi 7无线路由器 - 腾达(Tenda) 官方网站](https://www.tenda.com.cn/store/products/178)
2. 拆机：[腾达BE6L Pro 拆机云霄BE5100 W-Fi 7](https://www.acwifi.net/30262.html)
3. 内存颗粒数据手册：[M15T4G16256A(2P).pdf](https://www.eonssi.com/upload/pdf/ESMT/datasheets/M15T4G16256A(2P).pdf)
4. 2.5G PHY芯片的宣传页：[Product Info | Airoha Technology](https://www.airoha.com/products/p/tKkm7DPXi5m6wY2D)
