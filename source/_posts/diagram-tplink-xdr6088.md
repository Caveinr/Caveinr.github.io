---
title: TP-Link XDR6088的带宽分配
date: 2026-05-16 21:08:04
tags: 
  - 路由器
  - 拓扑图
index_img: 2026/diagram-tplink-xdr6088/diagram-tplink-xdr6088.png
---

# 带宽图解

{% asset_img diagram-tplink-xdr6088.png%}

注：虽然图中按照官方文档标注为SGMII，但就其速率而言应该是HiSGMII。


# 基本信息

```yaml
CPU:
  型号: MT7986A (MediaTek Filogic 830)
  架构: 四核 ARM Cortex-A53
  主频: 2.0 GHz
内存: 512 MB DDR4
存储: 128 MB 
无线规格:
  2.4GHz频段:
    规格: Wi-Fi 6 4x4 MIMO
    最大频宽: 40 MHz
    理论最大速率: 1147 Mbps
    FEM芯片: 未知
  5GHz频段:
    规格: Wi-Fi 6 4x4 MIMO
    最大频宽: 160 MHz
    理论最大速率: 4804 Mbps
    FEM芯片: QPF4588 (Qorvo)
  总无线速率: AX6000 (约 1147 Mbps + 4804 Mbps)
接口:
  以太网口:
    - 2.5 Gbps * 2
    - 1 Gbps * 4
  USB接口:
    速率: 5 Gbps
电源:
  输入: 12V / 4A
```

# 参考链接

1. [轻舟XDR6088拆机，双2.5G网口的无线路由器](https://www.acwifi.net/20864.html)
2. [MT7531的规格表](https://datasheet4u.com/datasheets/MediaTek/MT7531/1603028)