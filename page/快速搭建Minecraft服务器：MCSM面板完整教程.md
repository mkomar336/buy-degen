# 快速搭建Minecraft服务器：MCSM面板完整教程

## 前言

MCSManager是一款开源的Minecraft服务器管理面板，支持多种服务端版本，提供可视化操作界面，极大简化了MC服务器的搭建流程。

👉 [【点击查看】2025年最新雨云优惠码及特价云服务器方案汇总](https://bit.ly/RainYun)

## 环境准备

### 系统要求
- 推荐使用纯净的Ubuntu系统
- 建议配置：2核CPU/4GB内存/3M带宽及以上

## Java环境安装

### 版本选择指南
| Minecraft版本 | 所需Java版本 |
|---------------|-------------|
| 1.17以下      | Java 8      |
| 1.17及以上    | Java 16+    |

### 安装步骤（以Java 17为例）
bash
apt update
apt install -y openjdk-17-jdk
java -version

### 其他版本安装命令
bash
apt install openjdk-8-jdk   # Java 8
apt install openjdk-11-jdk   # Java 11

## MCSM面板部署

### 一键安装命令
bash
wget -qO- https://gitee.com/mcsmanager/script/raw/master/setup_cn.sh | bash

### 服务管理命令
bash
# 启动面板
systemctl start mcsm-{daemon,web}.service

# 设置开机自启
systemctl enable mcsm-{daemon,web}.service

# 重启特定服务
systemctl restart mcsm-web.service      # Web服务
systemctl restart mcsm-daemon.service   # 守护进程

> 访问地址：`http://服务器IP:23333/`

## 服务端安装指南

### 新手快速安装
1. 登录面板后选择"创建实例"
2. 从预设模板中选择合适的服务端版本
3. 配置基础参数（内存分配、端口等）
4. 启动实例并完成初始化设置

### 高级自定义安装
1. 下载官方服务端文件
2. 通过面板上传服务端软件包
3. 配置启动参数（特别是有mod的情况）
4. 管理EULA文件和其他配置文件

## 常见问题解决

1. **Java版本冲突**：确保安装与MC版本匹配的Java环境
2. **端口占用**：检查23333和25565端口是否被占用
3. **启动失败**：查看控制台日志定位具体问题
4. **性能优化**：根据在线人数调整JVM参数

## 服务器推荐配置

对于10-20人同时在线的服务器，建议选择：
- CPU：4核及以上
- 内存：8GB及以上
- 带宽：5Mbps及以上

👉 [立即获取高性能云服务器，畅玩Minecraft不卡顿](https://bit.ly/RainYun)

## 进阶配置

### 外置登录设置
1. 下载authlib-injector插件
2. 修改启动参数加入验证相关配置
3. 配置皮肤站实现完整的外置登录功能

### 自动化管理
- 设置定时重启
- 配置自动备份
- 监控服务器状态

> 提示：定期更新服务端和插件可提升安全性和稳定性