# 天翼智屏 ZXV10 S100V8H · VH8助手

天翼智慧屏VH8助手，通过链接安装到设备之后，可以实现
## 使用方法
安装 `VH8助手-v24.apk.part00…part08` 前先按文件名顺序合并成 APK，再安装到设备。打开后运行“一键完整配置”：验证厂商 root 通道、备份配置和关键 APK、安装 Aerial、修复公共 U 盘挂载、设置桌面/ADB 恢复/已识别 OTA 拦截。文件管理器需自行安装。电源按键单独测试短按熄屏与唤醒，通过后再启用。操作记录和备份路径在“更多”。

## 合并分卷
在 Windows PowerShell 中，在下载目录运行：
`Get-Content .\VH8助手-v24.apk.part* -AsByteStream | Set-Content .\VH8助手-v24.apk -AsByteStream`
源码压缩包同理，将文件名前缀替换为 `vh8-assistant-source.zip`。按下列 SHA-256 校验：
- APK：`50DF995C93765817DD796E4975D754492BA7BBE3848634B15B4D2B98EFA26F93`（2,962,714 字节）
- 源码 ZIP：`7F313FE41340A9CE1A15BA2B2E8D61D63AFF44BDFBD6B117F3A5EC2A49CC78A5`（2,941,910 字节）

## 源码构建
源码包含 Android 源码、power native、Aerial 离线包、运行资源及脚本。构建依赖 JDK、Android 28 SDK/aapt2、D8/R8、Python 与自行配置的签名密钥。私钥不包含在仓库内，工具链路径需自行调整。

## 限制与验证范围
Root 来自此固件厂商特权服务的本机 UID 0 命令通道，不是通用 Android root/Magisk。只对该型号和精确固件开放写操作。root UID 0、Aerial 主页、ADB 恢复、USB 自动入口、电源键熄屏/唤醒在现有设备验证；新设备首次完整配置及重启未端到端验证。OTA 仅拦截已识别入口。
