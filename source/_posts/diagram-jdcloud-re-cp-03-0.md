---
title: 京东云百里的带宽分配
date: 2026-05-16 22:45:31
tags: 
  - 路由器
  - 拓扑图
index_img: 2026/diagram-jdcloud-re-cp-03-0/diagram-jdcloud-re-cp-03-0.png
---

# 带宽图解

{% asset_img diagram-jdcloud-re-cp-03-0.png%}

注：
* 虽然图中按照官方文档标注为SGMII，但就其速率而言应该是HiSGMII。
* 观察拆机图，结合MT7531A的手册，可以确认是空置了MT7531的SGMII总线，使用了CPU的引出的该机唯一一个2.5G以太网口。

# 基本信息

```yaml
CPU:
  型号: MT7986A (MediaTek Filogic 830)
  架构: 四核 ARM Cortex-A53
  主频: 2.0 GHz
内存: 1 GB DDR4 3200
存储: 64/128 GB eMMC
无线规格:
  2.4GHz频段:
    规格: Wi-Fi 6 4x4 MIMO
    最大频宽: 40 MHz
    理论最大速率: 1147 Mbps
    FEM芯片: 康希通信 8247HE
  5GHz频段:
    规格: Wi-Fi 6 4x4 MIMO
    最大频宽: 160 MHz
    理论最大速率: 4804 Mbps
    FEM芯片: 康希通信 8575HE
  总无线速率: AX6000 (约 1147 Mbps + 4804 Mbps)
接口:
  以太网口:
    - 2.5 Gbps * 1
    - 1 Gbps * 4
电源:
  输入: 12V / 2A
```

# 参考链接

1. 64G规格的拆解 [京东云无线宝百里路由器拆解报告：全屋好信号，给生活加点“甜” ](https://post.smzdm.com/p/arqz269g/)
2. 128G规格的拆解 [无线宝百里AX6000拆解 ](https://post.smzdm.com/p/a4pdzqpx/)
2. [MT7531的规格表](https://datasheet4u.com/datasheets/MediaTek/MT7531/1603028)