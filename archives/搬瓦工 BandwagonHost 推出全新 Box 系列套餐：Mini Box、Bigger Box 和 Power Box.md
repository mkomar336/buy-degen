# 搬瓦工 BandwagonHost 推出全新 Box 系列套餐：Mini Box、Bigger Box 和 Power Box

今年双十一，搬瓦工推出的 Mini Box 内测产品凭借其实惠的价格和性能表现广受欢迎。紧接着，其又发布了升级版本的 Bigger Box 套餐和最新的 Power Box 套餐，为用户提供更多样化的选择。本文将详细介绍 Box 系列的相关信息以及购买建议。

## 新版 Power Box 套餐概览

搬瓦工于 2025 年 1 月 4 日新推出了 Power Box 套餐，其年付价格为 $45，使用优惠码后可降至 $41.95。同时，购买该套餐无需邀请码。现有的 Bigger Box 用户可以通过后台自动补差升级到 Power Box，而 Mini Box 用户则需提交工单实现套餐升级。

Box 系列套餐均部署在 DC99 数据中心（实际为 DC9，位于洛杉矶），去程线路采用电信 CN2 GIA、联通 AS4837 和移动 CMIN2，回程为全三网 CN2 GIA。虽然官方表明这是测试机型，并没有 SLA 服务和线路保证，但近年来的用户体验表明其总体稳定性相当出色。

👉 [【建议收藏】2025年搬瓦工最新优惠套餐整理汇总 - 每日更新最新可用优惠码](https://bit.ly/banwagon)

## 产品性能与网络测试

笔者在第一时间购入了 Mini Box，并使用至今，对其表现整体满意。以下是 Mini Box 的详细 YABS 测试数据：

Basic System Information:
---------------------------------
Processor  : AMD EPYC-Genoa Processor
CPU cores  : 1 @ 2794.748 MHz
RAM        : 536.7 MiB
Disk       : 10.2 GiB
Distro     : Debian GNU/Linux 12
Network    : 1Gb/s 国际带宽
...

从配置上来看，Mini Box 搭载 AMD EPYC 处理器，而 Bigger Box 和 Power Box 则是新一代的 Intel Xeon 处理器。不仅计算能力提升，Power Box 还将带宽升级至 2.5Gb/s，国际方向均为 10Gb/s，特别适合需要稳定跨境访问的电信和联通用户。不过，移动用户可能因晚高峰的 QoS 限制需要额外注意，建议选择 CMIN2 回程的套餐（如 DC6 或 DC9 数据中心）。

测试显示，搬瓦工 Box 系列产品在硬件性能和网络速度上较老套餐显著提升，尤其在国内 CN2 GIA 网络上的体验非常优秀。

## Box 系列套餐价格和优惠

以下为 Box 系列套餐的大致定价和热门优惠：

- Mini Box：年付 $27.04
- Bigger Box：年付 $34.5
- Power Box：年付 $41.95

优惠码：`BWHCGLUKKB`（享受 6.77% 循环折扣）

此外，Box 系列同样支持 30 天内退款政策——即使 IP 地址被墙也可退款（流量使用需低于 10%）。需要注意的是，部分套餐仅通过邀请码购买，以下为一些可用邀请码供您参考：

bwh_ScNZwCeEPFQQnhIR9g2BBMAG2XiR
bwh_f7QX9tNwWS0CnHiBPRjOXcgoOGVH
bwh_u3pz15n0p0ncIeEWLMoruy6hAcwf
...

## 购买建议

由于这是官方推出的内测系列，在活动结束后短期内很可能不会返场。如果您对 CN2 GIA VPS 有需求，建议尽快配置和下单。

综上，搬瓦工 Box 系列套餐无论是性能、网络还是价格性价比，均非常值得推荐。特别是 Power Box 套餐，提供了更高带宽和更强硬件配置，对于有跨境互联网需求的用户是一个极佳选择。