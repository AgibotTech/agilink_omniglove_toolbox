# Troubleshooting

[中文](../zh_cn/TROUBLESHOOTING.md) · [Quick Start](QUICK_START.md)

| Symptom | Check |
| --- | --- |
| Download checksum fails | Download the package and its matching version/name `.sha256` again, then follow the [platform instructions](../../README.md#platform-documentation). |
| Linux USB connection fails | The Debian installer configures permissions. For the portable package, run `sudo share/udev/install-usb-rules.sh`, then launch as a normal user. Reconnect and rescan if necessary. |
| Windows glove is not discovered | Check the connection, WinUSB.sys and device status, then **Rescan devices**. Check vendor drivers for CAN adapters. |
| Connected but no valid pose data | Check logs and quality. Device firmware must match the packaged OmniGlove SDK ABI 6.0.0; an application update cannot supply fields missing from older firmware. |
| No tactile data | Confirm that the glove has tactile sensors. Gloves without them do not need pressure zeroing and can use pose and model features. |
| Incorrect tactile baseline | Click **Zero pressure** and keep the glove free of contact for 2 seconds. Reconnection also recaptures the baseline. |
| Saved calibration has no effect | Click **Write to glove** and wait for readback verification. Import does not write automatically. If writing fails, check the connection and **Retry write to glove** without recapturing. |
| An operation is disabled | Follow the UI prompt: stop recording, **Return to live**, or wait for the running task to finish. |
| Simulation does not start | Check desktop/OpenGL drivers. Remove any `OMNIGLOVE_MUJOCO_PYTHON` override and restart to use the included runtime. |
| Dual-hand connection conflict | Use separate CAN adapter channels/adapters or serial ports. A shared SocketCAN interface requires different device IDs. |
| Firmware versions are unavailable | Current versions cannot be read in DFU mode; identify the target by USB location. In normal mode, connect, refresh and inspect update logs. |

## Linux Graphics

If the portable package reports missing xcb / OpenGL libraries:

```bash
sudo apt update
sudo apt install libxcb-cursor0 libxcb-xinerama0 libxkbcommon-x11-0 libopengl0 libgl1 libegl1 libfontconfig1 libdbus-1-3
```

For OpenGL initialization failures, try software OpenGL with 3D support:

```bash
LIBGL_ALWAYS_SOFTWARE=1 ./run.sh
```

Software rendering may reduce 3D performance. With DISPLAY available, the launcher defaults to X11/XWayland. To select Wayland explicitly, use `QT_QPA_PLATFORM=wayland ./run.sh`.

Use **Logs** to inspect errors and sources. Include the platform, application version, device SN, firmware versions and attempted operation when reporting a problem.
