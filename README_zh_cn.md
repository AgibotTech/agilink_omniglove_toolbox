# AGILINK OmniGlove Toolbox

[English Documentation](README.md)

OmniGlove Toolbox 是用于连接 OmniGlove 手套、查看触觉与运动数据、个人标定、OmniHand 遥操作及固件升级的桌面上位机。本仓库提供 **v1.0.1** 安装包与使用文档。

## 快速链接

- [快速入门指南](doc/zh_cn/QUICK_START.md)
- [故障排除](doc/zh_cn/TROUBLESHOOTING.md)
- [下载 v1.0.1](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/tag/v1.0.1)
- [版本说明](CHANGELOG.md)

## 下载

| 平台 | 安装包 | SHA-256 |
| --- | --- | --- |
| Ubuntu 22.04 / 24.04 x86_64 | [Debian 安装包](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.1/omniglove-toolbox_1.0.1-1_amd64.deb) | [校验文件](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.1/omniglove-toolbox_1.0.1-1_amd64.deb.sha256) |
| Ubuntu 22.04 / 24.04 x86_64 | [tar.gz 便携包](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.1/omniglove-toolbox-1.0.1-linux-x86_64.tar.gz) | [校验文件](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.1/omniglove-toolbox-1.0.1-linux-x86_64.tar.gz.sha256) |
| Windows x64 | [安装程序](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.1/omniglove-toolbox-1.0.1-windows-x86_64-setup.exe) | [校验文件](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.1/omniglove-toolbox-1.0.1-windows-x86_64-setup.exe.sha256) |
| Windows x64 | [ZIP 便携包](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.1/omniglove-toolbox-1.0.1-windows-x86_64.zip) | [校验文件](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.1/omniglove-toolbox-1.0.1-windows-x86_64.zip.sha256) |

## 平台文档

- [Linux x64 / amd64](linux/x64/README_zh_cn.md)：安装、USB 权限与文件校验。
- [Windows x64](windows/x64/README_zh_cn.md)：安装、WinUSB 驱动与文件校验。

安装包已包含 Qt/QML、OmniGlove、OmniHand 和 MuJoCo 仿真运行环境，无需另外安装 Qt、SDK、Python 或 pip。设备驱动及桌面图形环境仍需按目标机器配置。Linux 最低 glibc 为 2.35；当前不提供 ARM 或 macOS 安装包。

## 主要功能

- 按 SN 识别并连接手套，支持左手、右手及多设备。
- 查看触觉分布、POST 手部模型、POST/POSE 抗磁对比和指尖运动轨迹。
- 完成六动作个人标定，确认后主动将结果写入手套。
- 使用 `.ogrecord` 同步录制与回放触觉、模型和指尖数据，可同时导出 BVH。
- 支持 OmniHand 2025（O10）、Ultra T1.3、Ultra T1.5、Lite 的仿真及实机遥操作，并可用 `.ogteleop` 录制、回放手套输入。
- 校验并升级设备固件，支持 BIN/HEX 文件。

具体操作见[快速入门指南](doc/zh_cn/QUICK_START.md)。

## 仓库结构

```text
README.md / README_zh_cn.md
LICENSE / THIRD_PARTY_NOTICES.md / CHANGELOG.md
doc/en/                  英文使用文档
doc/zh_cn/               中文使用文档
linux/x64/               Linux 安装包和校验文件
windows/x64/             Windows 安装包和校验文件
```

v1.0.1 安装包请使用上方 Release 下载链接。平台目录中保留的历史安装包通过 Git LFS 保存。

## 许可证

[木兰宽松许可证，第 2 版（Mulan PSL v2）](LICENSE) — Copyright (c) 2026, Agibot Co., Ltd. 第三方组件保留各自许可证，见[第三方声明](THIRD_PARTY_NOTICES.md)及安装包内的许可文件。
