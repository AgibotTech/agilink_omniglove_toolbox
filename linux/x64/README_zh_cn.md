# Linux x64 安装

[English](README.md) · [首页](../../README_zh_cn.md) · [使用说明](../../doc/zh_cn/QUICK_START.md)

适用于 Ubuntu 22.04 / 24.04 x86_64 桌面系统，最低 glibc 2.35。需要可用的 OpenGL/EGL 图形驱动。

从 [v1.0.1 Release](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/tag/v1.0.1) 下载所选安装包及同名 `.sha256` 文件。

## Debian 安装包

在下载目录执行：

```bash
sha256sum --check omniglove-toolbox_1.0.1-1_amd64.deb.sha256
sudo apt install ./omniglove-toolbox_1.0.1-1_amd64.deb
```

安装后从 Ubuntu 应用列表启动 **OmniGlove Toolbox**。安装器自动配置手套运行模式和 DFU 模式的 USB 权限，之后以普通用户运行。

## tar.gz 便携包

```bash
sha256sum --check omniglove-toolbox-1.0.1-linux-x86_64.tar.gz.sha256
tar -xzf omniglove-toolbox-1.0.1-linux-x86_64.tar.gz
cd omniglove-toolbox-1.0.1-linux-x86_64
sudo share/udev/install-usb-rules.sh
./run.sh
```

USB 权限只需配置一次。保留完整解压目录，无需另外安装 Qt、SDK 或 Python。

## 卸载

先退出应用及仿真、固件工具。安装版执行 `sudo apt remove omniglove-toolbox`；便携版执行 `./uninstall.sh`。录制、标定、设置及未列入包清单的额外用户文件默认保留。手工安装的 USB 规则可用 `sudo share/udev/uninstall-usb-rules.sh` 撤销，需在删除便携包前执行。

设备、图形或启动问题见[故障排除](../../doc/zh_cn/TROUBLESHOOTING.md)。
