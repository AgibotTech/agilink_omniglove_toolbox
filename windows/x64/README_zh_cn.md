# Windows x64 安装

[English](README.md) · [首页](../../README_zh_cn.md) · [使用说明](../../doc/zh_cn/QUICK_START.md)

适用于 Windows x64。安装包包含 Qt、SDK、VC++ 运行库及仿真运行环境；设备驱动和 OpenGL 图形驱动需按硬件配置。

从 [v1.0.0 Release](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/tag/v1.0.0) 下载所选安装包及同名 `.sha256` 文件。

## 校验文件

在下载目录用 PowerShell 校验安装程序：

```powershell
$package = 'omniglove-toolbox-1.0.0-windows-x86_64-setup.exe'
$expected = ((Get-Content -LiteralPath ($package + '.sha256') -Raw).Trim() -split '\s+')[0]
$actual = (Get-FileHash -LiteralPath $package -Algorithm SHA256).Hash
if ($actual -ine $expected) { throw 'SHA-256 校验失败' }
'SHA-256 校验通过'
```

校验 ZIP 时将 `$package` 改为 `omniglove-toolbox-1.0.0-windows-x86_64.zip`。

## 安装程序

双击 `omniglove-toolbox-1.0.0-windows-x86_64-setup.exe`，选择中文或英文并完成管理员认证。默认安装到 `Program Files\OmniGlove Toolbox`，安装后从开始菜单启动。

已有安装会提示升级、同版重装或降级；更新前先退出程序。未知非空目录或用户文件冲突会阻止覆盖，历史便携包缺少清单时请选择新的空目录。

## ZIP 便携包

完整解压 `omniglove-toolbox-1.0.0-windows-x86_64.zip`，双击包根目录的 `OmniGloveToolbox.exe`。保留所有 DLL、`plugins`、`qml` 和 `share` 目录。

## 手套驱动与数据

手套须使用 **WinUSB.sys**，上位机安装器不会安装或更改 USB 驱动。CAN 适配器需供应商驱动；SocketCAN 仅在 Linux 提供。串口名称可填写 `COM3` 等实际端口。

用户录制、标定、设置与日志保存在 `%LOCALAPPDATA%\OmniGlove\OmniGlove Toolbox`。

## 卸载

先退出程序。安装版从 Windows 应用列表或开始菜单卸载，也可运行安装目录的 `Uninstall.exe`；便携版运行包根目录的 `uninstall.bat`。额外用户文件及上述用户数据默认保留，硬件驱动不会被删除。

连接或启动问题见[故障排除](../../doc/zh_cn/TROUBLESHOOTING.md)。
