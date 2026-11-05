# Windows x64 Installation

[中文](README_zh_cn.md) · [Home](../../README.md) · [Usage](../../doc/en/QUICK_START.md)

For Windows x64. Qt, SDKs, VC++ libraries and the simulation runtime are included. Configure device and OpenGL graphics drivers for the hardware.

Download a package and its matching `.sha256` file from the [v1.0.0 Release](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/tag/v1.0.0).

## Verify a Download

In the download directory, verify the installer with PowerShell:

```powershell
$package = 'omniglove-toolbox-1.0.0-windows-x86_64-setup.exe'
$expected = ((Get-Content -LiteralPath ($package + '.sha256') -Raw).Trim() -split '\s+')[0]
$actual = (Get-FileHash -LiteralPath $package -Algorithm SHA256).Hash
if ($actual -ine $expected) { throw 'SHA-256 verification failed' }
'SHA-256 verified'
```

For the ZIP, set `$package` to `omniglove-toolbox-1.0.0-windows-x86_64.zip`.

## Setup Installer

Run `omniglove-toolbox-1.0.0-windows-x86_64-setup.exe`, choose Chinese or English and complete administrator authentication. The default location is `Program Files\OmniGlove Toolbox`. Launch from the Start menu.

Existing installations prompt for an upgrade, reinstall or downgrade; close the application first. Unknown nonempty folders and user-file conflicts block overwriting. Use a new empty folder for a historical portable package without a manifest.

## Portable ZIP

Extract the complete `omniglove-toolbox-1.0.0-windows-x86_64.zip` and run `OmniGloveToolbox.exe` in its root. Keep all DLLs and the `plugins`, `qml` and `share` directories.

## Glove Drivers and Data

Gloves require **WinUSB.sys**. The Toolbox installer does not install or change USB drivers. CAN adapters need vendor drivers; SocketCAN is available only on Linux. Use the actual serial name, such as `COM3`.

User recordings, calibration, settings and logs are stored in `%LOCALAPPDATA%\OmniGlove\OmniGlove Toolbox`.

## Uninstall

Close the application first. Uninstall the setup version through Windows Apps, the Start menu or `Uninstall.exe` in its installation folder. For the portable package, run `uninstall.bat`. Extra user files and application data are preserved by default; hardware drivers are retained.

See [Troubleshooting](../../doc/en/TROUBLESHOOTING.md) for connection or startup problems.
