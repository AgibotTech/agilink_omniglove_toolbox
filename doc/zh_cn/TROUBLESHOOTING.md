# 常见问题

[English](../en/TROUBLESHOOTING.md) · [快速入门](QUICK_START.md)

| 现象 | 检查方法 |
| --- | --- |
| 下载校验失败 | 重新下载安装包和同版本同名 `.sha256`，按[平台文档](../../README_zh_cn.md#平台文档)重新校验。 |
| Linux 无法连接 USB | Debian 安装版会自动设置权限；仅使用便携包时执行 `sudo share/udev/install-usb-rules.sh`。随后以普通用户启动，必要时重新插拔并重新识别。 |
| Windows 未发现手套 | 检查连接、WinUSB.sys 及设备状态，再点击 **重新识别**；CAN 适配器检查供应商驱动。 |
| 已连接但没有有效姿态 | 查看日志与数据质量，确认设备固件协议匹配包内 OmniGlove SDK ABI 6.0.0；仅升级上位机不能补齐旧固件缺少的数据字段。 |
| 没有触觉数据 | 先确认手套是否为有触觉版本。无触觉版本无需压力置零，可正常使用姿态和模型。 |
| 触觉基准不正确 | 点击 **压力置零**，保持手套无接触 2 秒；每次重连也会重新采集。 |
| 标定保存后没有生效 | 点击 **写入手套** 并等待读回校验通过；导入文件也不会自动写入。写入失败可检查连接后 **重试写入手套**，无需重新采集。 |
| 操作按钮不可用 | 按界面提示停止录制、点击 **返回实时** 或等待当前任务结束。 |
| 仿真无法启动 | 检查桌面和 OpenGL 驱动。若设置过 `OMNIGLOVE_MUJOCO_PYTHON`，移除该覆盖并重启，恢复包内运行环境。 |
| 双手遥操连接冲突 | CAN 适配器使用不同通道或适配器；串口使用不同路径；同一 SocketCAN 接口配置不同设备 ID。 |
| 固件页无法读取版本 | DFU 模式无法读取当前版本；按 USB 位置确认目标。普通模式可连接后刷新，并查看升级日志。 |

## Linux 图形环境

便携包提示缺少 xcb / OpenGL 库时，可安装：

```bash
sudo apt update
sudo apt install libxcb-cursor0 libxcb-xinerama0 libxkbcommon-x11-0 libopengl0 libgl1 libegl1 libfontconfig1 libdbus-1-3
```

若 OpenGL 初始化失败，可尝试保留 3D 功能的软件 OpenGL：

```bash
LIBGL_ALWAYS_SOFTWARE=1 ./run.sh
```

软件渲染可能降低 3D 性能。应用默认在有 DISPLAY 时使用 X11/XWayland；需要显式使用 Wayland 时执行 `QT_QPA_PLATFORM=wayland ./run.sh`。

排查时在 **日志** 页查看错误与来源，并记录平台、上位机版本、设备 SN、设备固件版本和具体操作。
