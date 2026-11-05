# AGILINK OmniGlove Toolbox

[中文文档](README_zh_cn.md)

OmniGlove Toolbox is the desktop application for connecting OmniGlove gloves, viewing tactile and motion data, personal calibration, OmniHand teleoperation, and firmware updates. This repository provides **v1.0.0** installation packages and usage documentation.

## Quick Links

- [Quick Start Guide](doc/en/QUICK_START.md)
- [Troubleshooting](doc/en/TROUBLESHOOTING.md)
- [Download v1.0.0](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/tag/v1.0.0)
- [Release Notes](CHANGELOG.md)

## Downloads

| Platform | Package | SHA-256 |
| --- | --- | --- |
| Ubuntu 22.04 / 24.04 x86_64 | [Debian installer](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.0/omniglove-toolbox_1.0.0-1_amd64.deb) | [Checksum](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.0/omniglove-toolbox_1.0.0-1_amd64.deb.sha256) |
| Ubuntu 22.04 / 24.04 x86_64 | [Portable tar.gz](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.0/omniglove-toolbox-1.0.0-linux-x86_64.tar.gz) | [Checksum](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.0/omniglove-toolbox-1.0.0-linux-x86_64.tar.gz.sha256) |
| Windows x64 | [Setup installer](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.0/omniglove-toolbox-1.0.0-windows-x86_64-setup.exe) | [Checksum](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.0/omniglove-toolbox-1.0.0-windows-x86_64-setup.exe.sha256) |
| Windows x64 | [Portable ZIP](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.0/omniglove-toolbox-1.0.0-windows-x86_64.zip) | [Checksum](https://github.com/AgibotTech/agilink_omniglove_toolbox/releases/download/v1.0.0/omniglove-toolbox-1.0.0-windows-x86_64.zip.sha256) |

## Platform Documentation

- [Linux x64 / amd64](linux/x64/README.md): installation, USB permissions, and checksums.
- [Windows x64](windows/x64/README.md): installation, WinUSB, and checksums.

The packages include Qt/QML, the OmniGlove and OmniHand runtimes, and the MuJoCo simulation runtime. No separate Qt, SDK, Python, or pip installation is required. Hardware drivers and a working desktop graphics environment are required. Linux requires glibc 2.35 or newer; ARM and macOS packages are not provided.

## Main Features

- Discover gloves by SN and connect left, right, or multiple devices.
- View tactile maps, POST hand models, POST/POSE magnetic interference comparison, and fingertip trajectories.
- Complete six-step personal calibration and explicitly write the result to the glove.
- Record and replay synchronized data as `.ogrecord`, with optional BVH export.
- Teleoperate OmniHand 2025 (O10), Ultra T1.3, Ultra T1.5, and Lite in simulation or with hardware; record and replay glove inputs as `.ogteleop`.
- Validate and update device firmware using BIN/HEX files.

See the [Quick Start Guide](doc/en/QUICK_START.md) for the v1.0.0 workflow.

## Repository Layout

```text
README.md / README_zh_cn.md
LICENSE / THIRD_PARTY_NOTICES.md / CHANGELOG.md
doc/en/                  English usage documentation
doc/zh_cn/               Chinese usage documentation
linux/x64/               Linux packages and checksums
windows/x64/             Windows packages and checksums
```

Installation packages are tracked with Git LFS. For a local repository checkout, install Git LFS before cloning, then run `git lfs pull`. For installation, use the Release downloads above.

## License

[Mulan PSL v2](LICENSE) — Copyright (c) 2026, Agibot Co., Ltd. Third-party components retain their own licenses; see [Third-Party Notices](THIRD_PARTY_NOTICES.md) and the license files included in each package.
