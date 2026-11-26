# 天翼智屏 ZXV10 S100V8H 工具集

个人备份仓库，包含 VH8 助手、智屏信息板、构建所需源码/资源与安装包。目标设备实测环境：ZXV10 S100V8H，Android 9 / API 28，固件指纹 `ZTE/rk356x_box_32/rk356x_box_32:9/PI/20260817:user/release-keys`。写入功能只对精确型号及该固件指纹开放。

## 快速使用

### VH8 助手

安装根目录 `VH8助手-v24.apk`，在设备上打开并运行“一键完整配置”。应用按顺序验证厂商 root 命令通道、备份设置和关键 APK、安装 Aerial、修复公共 U 盘挂载并设置插入后打开文件管理器、固化主页、恢复 ADB、拦截已识别 OTA 入口。文件管理器需要用户自行安装。随后单独进入电源键功能，先做实体短按熄屏/唤醒测试，通过后再启用。操作历史在“更多”中查看。

Root 是本固件厂商特权服务提供的本机 UID 0 命令通道，不是通用 Android root/Magisk。代码没有解锁或刷写系统分区功能。其他固件会拒绝写操作。

### 智屏信息板

安装 `智屏信息板-v13.apk`。进入“··· → 设置 → 数据”，配置 GitHub 只读令牌（仅限仓库 Contents read），关闭演示模式并保存。当前每分钟条件检查 GitHub Contents；使用 ETag、保留最近有效缓存、手动刷新。仓库快照格式及服务器端生成补丁位于信息板源码包中。令牌只存在于设备 Android Keystore 加密配置中，不要放进仓库。

## 源码包与重建

`vh8-assistant-source.zip` 包含 VH8 Android 源码、power native 部分、Aerial 离线 APK、运行资源及构建脚本。`information-panel-source.zip` 包含 Android/Web2 界面、服务器快照生成补丁和构建脚本。构建脚本依赖 JDK、Android 28 SDK build-tools/aapt2、D8/R8、Python，以及设备签名密钥。私钥不在仓库内；需自行创建并调整脚本中的本机工具链/签名密钥路径。源码包中的构建脚本是此工作站版本，须按自己的环境配置。

## 已验证边界

现有设备曾验证 root 通道 UID 0、Aerial 主页接管/开机行为、ADB 恢复、USB 自动入口、电源键熄屏与唤醒以及信息板 GitHub 只读同步。VH8 新版本完整初始化在全新出厂设备的首次安装与重启恢复尚未做端到端验收；OTA 拦截只覆盖反编译确认的若干入口，不保证覆盖厂商所有升级路径。仓库内容是个人备份，使用者应先保存自己的配置并逐步验证。

## 目录

- `VH8助手-v24.apk`：VH8 助手安装包
- `智屏信息板-v13.apk`：信息展示安装包
- `vh8-assistant-source.zip`：VH8 源码和资源
- `information-panel-source.zip`：信息板与服务端补丁源码

