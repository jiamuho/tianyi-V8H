# 天翼智屏 ZXV10 S100V8H · VH8助手

仅包含 VH8 助手的个人备份。目标环境：ZXV10 S100V8H、Android 9/API 28、固件指纹 `ZTE/rk356x_box_32/rk356x_box_32:9/PI/20260817:user/release-keys`。

## 使用

在智屏安装 `VH8助手-v24.apk)，打开后点击“一键完整配置”。应用依次验证本机厂商 root 通道、备份配置与关键 APK、安装 Aerial、修复公共 U 盘挂载、设置主页和 ADB 开机恢复、拦截已识别的 OTA 入口。文件管理器需自行安装。电源键功能需单独做实体按键测试，通过后再启用。

Root 来自本固件厂商特权服务的 UID 0 命令通道，不是通用 Android root 或 Magisk。写操作仅对已核验型号和固件开放；不可刷写系统分区。请在“更多”查看操作记录与备份路径。

## 文件

- `VH8助手-v24.apk`：设备安装包
- `vh8-assistant-source.zip`：VH8 源码、资源与构建脚本

源码构建需要 JDK、Android 28 SDK build-tools/aapt2、D8/R8、Python 和自行配置的签名密钥。私钥没有放入备份。构建脚本中的工具链路径需按本机环境调整。

## 验证范围

root UID 0、Aerial 主页接管、ADB 恢复、USB 自动入口、电源键熄屏/唤醒已在现有设备验证。全新设备完整初始化与新版本整机重启尚未端到端验收；OTA 拦截只覆盖已识别入口。