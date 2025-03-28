# 零基础Windows搭建幻兽帕鲁服务器：雨云VPS保姆级教程

## 幻兽帕鲁游戏简介

《幻兽帕鲁》是由Pocketpair开发的一款开放世界生存制作游戏，于2024年1月18日发布抢先体验版。这款游戏融合了宠物收集、战斗和建造等多元玩法，支持多人在线联机，成为近期热门游戏。

**核心特色**：
- 独特的帕鲁系统：可捕捉、培养和指挥帕鲁进行战斗和工作
- 丰富的生存要素：建造、耕种、制造等多样化玩法
- 多人联机功能：支持32人同时在线游玩
- 开放世界探索：广阔的地图供玩家自由冒险

👉 [【点击查看】2025年最新雨云优惠码及特价云服务器方案汇总](https://bit.ly/RainYun)

## 准备工作

### 1. 选择云服务器配置

**推荐配置**：
- **CPU**：4核及以上（官方推荐4核16G）
- **内存**：8GB起步（32GB更佳）
- **系统**：Windows Server 2019
- **网络**：建议选择靠近玩家的服务器区域

**优惠信息**：
使用优惠码"ryy"注册可获5折优惠券

### 2. 购买服务器流程
1. 登录雨云控制台
2. 进入"游戏云"板块
3. 选择VPS服务器
4. 配置选择：
   - 机型：14900KF/13900KF/Ryzen 7950X等
   - 计费模式：固定计费（长期玩）或动态计费（偶尔玩）
5. 完成购买

## 服务器设置指南

### 1. 远程连接服务器
使用Windows自带的远程桌面连接(RDP)：
1. 打开"远程桌面连接"
2. 输入服务器IP和端口（默认3389）
3. 用户名：Administrator
4. 输入密码连接

### 2. 防火墙配置
1. 打开"高级安全Windows Defender防火墙"
2. 将所有配置文件的防火墙状态设为"关闭"
3. 或仅开放8211端口（游戏端口）

### 3. 端口映射设置
1. 进入NAT端口映射
2. 新建规则：
   - 内网端口：8211
   - 外网端口：自动生成
3. 保存设置

## 一键部署服务端

### 使用PowerShell脚本部署
1. 右键开始菜单，选择"Windows PowerShell"
2. 运行一键部署命令：
   powershell
   iex (New-Object Net.WebClient).DownloadString('https://example.com/palworld-install.ps1')
   
3. 等待安装完成（约10-30分钟）
4. 出现"PalServer deploy success!"提示即成功

**安装路径**：`C:\Program Files\PalServer`

## 游戏参数配置

### 修改服务器设置
1. 找到配置文件：
   `C:\Program Files\PalServer\steam\steamapps\common\PalServer\DefaultPalWorldSettings.ini`
2. 复制到：
   `C:\Program Files\PalServer\steam\steamapps\common\PalServer\Pal\Saved\Config\WindowsServer`
3. 重命名为：`PalWorldSettings.ini`
4. 修改关键参数：
   ini
   OptionSettings=(Difficulty=None,
       ExpRate=1.000000,       ; 经验倍率
       PalCaptureRate=1.000000, ; 捕捉概率
       ServerPlayerMaxNum=32,   ; 最大玩家数
       ServerName="My Server",  ; 服务器名称
       PublicPort=8211          ; 游戏端口
   )
   
5. 保存后重启服务器生效

## 服务器管理技巧

### 常用管理员命令
| 命令 | 功能 |
|------|------|
| `/Broadcast 消息` | 全服广播 |
| `/KickPlayer SteamID` | 踢出玩家 |
| `/BanPlayer SteamID` | 封禁玩家 |
| `/Save` | 手动保存数据 |
| `/Shutdown 60 "服务器维护"` | 定时关闭 |

### 内存优化方案
1. **设置虚拟内存**：
   - 初始大小：物理内存1.5倍
   - 最大值：物理内存3倍

2. **自动重启脚本**：
   powershell
   # 内存超过90%时自动重启
   while($true) {
       $mem = (Get-Counter '\Memory\% Committed Bytes In Use').CounterSamples.CookedValue
       if($mem -gt 90) {
           Restart-Service PalServer -Force
           Start-Sleep 300
       }
       Start-Sleep 60
   }
   

## 服务端更新方法
在PowerShell中运行更新命令：
powershell
iex (New-Object Net.WebClient).DownloadString('https://example.com/palworld-update.ps1')

等待完成后重启服务器即可。

## 常见问题解答

**Q：连接服务器时提示超时怎么办？**
A：检查防火墙设置和端口映射是否正确，确保8211端口已开放

**Q：游戏卡顿如何解决？**
A：建议升级服务器配置，或减少同时在线玩家数量

**Q：如何备份游戏存档？**
A：存档位置：`C:\Program Files\PalServer\steam\steamapps\common\PalServer\Pal\Saved\SaveGames`

通过本教程，您已掌握在雨云VPS上搭建幻兽帕鲁服务器的完整流程。现在就可以邀请好友一起体验这款热门游戏了！