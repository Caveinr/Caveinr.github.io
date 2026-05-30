---
title: 华擎B550 幻影电竞 ITX/AX
date: 2026-05-24 17:43:32
tags: 
  - 主板
  - 拓扑图
---
# 基本信息

## 供电

接口:

```yaml
CPU: 8 Pin
ATX: 24 Pin
```

IC:

```yaml
PWM: 瑞萨 RAA229004
  CORE MOS: 瑞萨 ISL99390 *6
  SOC/GT MOS: 瑞萨 ISL99227 *2
RAM Converter: 芯源 MPQ8633B
```

## 扩展

```yaml
后置:
  以太网: I225-V 2.5G
  无线网卡: AX200 Wi-Fi 6 2x2
  USB:
    - 10G Type-A *1
    - 10G Type-C *1
    - 5G Type-A *4
  视频:
    - HDMI 2.1 *1
    - DP 1.4 *1
板载:
  USB:
    - 10G 3.0 Type-E接针 *1
    - 5G 3.0 19Pin接针 *1
    - 480M 2.0 9Pin接针 *1
  PCIe:
    - 4.0 x16 *1
  存储:
    - M.2 4.0x4 带散热片 *1
    - M.2 3.0x4/SATA3 *1
    - SATA3 *4
```

## 外围

```yaml
风扇:
  - 4Pin *3
RGB:
  - 12V RGB
  - 5V ARGB
音频: 
  ALC1220:
    - 后置 3 Pin
    - 板载 HD Audio
其它:
  - 板载CLRCMOS
```

# 通道拓扑

{% asset_img diagram-asrock-b550-phantom-gaming-itx-ac.png%}

注：

* 只给出了5000系 `Vermeer`和3000系 `Matisse`的拓扑情况
* 中继芯片等和带宽无关的芯片都没有画出

# 参考链接

1. 华擎官网：[华擎科技 | B550 幻影电竞-ITX/ax](https://pg.asrock.com/mb/AMD/B550%20Phantom%20Gaming-ITXax/index.cn.asp)
2. AMD 5000发布会的PPT：[Techpowerup源](https://www.techpowerup.com/268590/amd-b550-chipset-motherboards-start-selling)
3. Techpowerup对AM4芯片组带宽的[一图流](https://tpucdn.com/cpu-specs/images/connectivity/amd-am4.png)（需要指出的是B550多了一组PCIe3.0 x4，参考上一条）
4. 拆解：知乎[高规格？性价比？我全都要！华擎 B550 Phantom Gaming-ITX/ax 拆解评测](https://www.zhihu.com/tardis/zm/art/210217417)
