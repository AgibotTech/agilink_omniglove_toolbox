# Release Notes / 版本说明

## v1.0.1 — 2026-11-09

- 优化 Ultra / Lite 遥操作兼容性与连接诊断。
- 串口列表增加设备名称及可用 SN，简化设备 ID 标签。
- 完善中英文界面与日志，优化触觉布局和标定完成提示。
- 改进 Windows 安装向导、应用图标和快捷方式设置。

Improved Ultra/Lite teleoperation compatibility, serial device identification, interface translations, calibration feedback, and Windows installation.

提供 Linux tar.gz / Debian 安装包、Windows ZIP / 安装程序及对应 SHA-256 校验文件。

## v1.0.0 — 2026-11-05

Initial public package release of OmniGlove Toolbox. / OmniGlove Toolbox 首次公开安装包发布。

- Ubuntu 22.04 / 24.04 x86_64: portable tar.gz and Debian installer; Windows x64: portable ZIP and setup installer. Each package includes a SHA-256 checksum file.
- SN-based device discovery, tactile maps, POST models and POST/POSE comparison, fingertip trajectories, six-step calibration, `.ogrecord` recording/playback and optional BVH export.
- O10, Ultra T1.3, Ultra T1.5 and Lite teleoperation with included MuJoCo simulation, plus `.ogteleop` input recording/playback.
- Device firmware validation and update using BIN/HEX files.
- OmniGlove SDK ABI 6.0.0; Linux glibc baseline 2.35. The included `BUILD_INFO.txt` identifies each platform build.
- English and Chinese installation, quick-start and troubleshooting documents; Mulan PSL v2 license and third-party notice index.

提供 Linux tar.gz / Debian 安装包、Windows ZIP / 安装程序及各自 SHA-256 校验文件；涵盖按 SN 连接、实时数据查看、六动作标定、录制回放、四型号遥操与仿真、固件升级。应用运行库和仿真环境随包部署，设备驱动仍需按硬件配置。

Release packages are uploaded unchanged. Device connection, calibration writing, firmware updating and physical teleoperation depend on the target hardware and firmware; no additional hardware acceptance testing is claimed by this distribution repository.

发布包保持原始文件内容。设备连接、标定写入、固件升级及实机遥操依赖目标硬件和设备固件，本发行仓库不额外声明实物验收结果。

