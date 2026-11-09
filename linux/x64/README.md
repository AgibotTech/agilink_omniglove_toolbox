# Linux x64 Installation

[中文](README_zh_cn.md) · [Home](../../README.md) · [Usage](../../doc/en/QUICK_START.md)

For Ubuntu 22.04 / 24.04 x86_64 desktops with glibc 2.35 or newer and working OpenGL/EGL graphics drivers.

Download a package and its matching `.sha256` file from the [v1.0.1 Release](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/tag/v1.0.1).

## Debian Installer

Run in the download directory:

```bash
sha256sum --check omniglove-toolbox_1.0.1-1_amd64.deb.sha256
sudo apt install ./omniglove-toolbox_1.0.1-1_amd64.deb
```

Launch **OmniGlove Toolbox** from the Ubuntu application launcher. Installation configures glove USB permissions for normal and DFU modes; run the application as a normal user afterward.

## Portable tar.gz

```bash
sha256sum --check omniglove-toolbox-1.0.1-linux-x86_64.tar.gz.sha256
tar -xzf omniglove-toolbox-1.0.1-linux-x86_64.tar.gz
cd omniglove-toolbox-1.0.1-linux-x86_64
sudo share/udev/install-usb-rules.sh
./run.sh
```

USB permission setup is needed once. Keep the entire extracted directory; Qt, SDKs and Python do not need separate installation.

## Uninstall

Close the application, simulation and firmware tools first. Use `sudo apt remove omniglove-toolbox` for the installer, or `./uninstall.sh` for the portable package. Recordings, calibration, settings and extra user files outside the package manifest are preserved by default. To remove manually installed USB rules, run `sudo share/udev/uninstall-usb-rules.sh` before removing the portable package.

See [Troubleshooting](../../doc/en/TROUBLESHOOTING.md) for device, graphics or startup problems.
