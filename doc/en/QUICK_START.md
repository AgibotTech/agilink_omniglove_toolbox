# OmniGlove Toolbox v1.0.0 Quick Start

[中文](../zh_cn/QUICK_START.md) · [Home](../../README.md)

## 1. Install and Connect

Install the [Linux](../../linux/x64/README.md) or [Windows](../../windows/x64/README.md) package and launch OmniGlove Toolbox. Application libraries and the simulation runtime are included.

Connect the glove. In **Settings**, check each discovered device's SN, hand and versions, then click **Connect** or **Connect all devices**. Use **Rescan devices** if necessary. When multiple gloves share a hand, select the source SN in the data views.

Tactile gloves zero automatically when valid data first arrives and after each reconnection. Keep the glove free of contact for **2 seconds**. Gloves without tactile sensors can use pose and model features directly.

## 2. View Live Data

| Page | Usage |
| --- | --- |
| **Pressure** | View left/right tactile maps and trend charts. Click **Zero pressure** to recapture a baseline, keeping the glove free of contact for 2 seconds. Values from 0–255 are sensor tactile readings; gray means no data. |
| **Model** | Drag to rotate and scroll to zoom. Choose visible hands, tactile points, wrist orientation and joint angle details. SDK POST is shown by default; **Magnetic interference comparison** adds local POSE solving beside POST. |
| **Trajectory** | View fingertip landmarks, axes and local trails in the wrist frame. Coordinates use millimetres and the wrist stays at the origin. |
| **Logs** | Inspect device and operation logs; filter by level, source or keyword. |

## 3. Six-Step Personal Calibration

Open **Calibration**, select the hand and calibration root folder, and click **Start calibration**. Follow the on-screen cues:

1. Keep four fingers straight and together; hold still.
2. Flex at the four base knuckles and straighten twice, keeping the other joints straight.
3. Touch the thumb tip to the index fingertip; hold steady.
4. Touch the thumb tip to the middle fingertip; hold steady.
5. Touch the thumb tip to the ring fingertip; hold steady.
6. Touch the thumb tip to the little fingertip; hold steady.

Release each pinch completely before the next cue. Review valid samples, quality and fitting results. Once the file is saved, click **Write to glove** and wait for successful writing and readback verification. **Capturing or saving alone does not apply the new calibration.**

Use **Import existing calibration** for an existing `.ogcal` file. Import only validates the file; confirm the target hand and click **Write to glove**. Calibrate and write each hand separately.

## 4. Record and Replay

In a data view, click **Record to file** and select a file. **Stop and save** creates an `.ogrecord` recording. Enable **Also export BVH** for an additional motion file.

Use **Open recording** for offline playback, pause and seek. Tactile, model and fingertip views stay synchronized. Click **Return to live** before live recording, calibration or firmware operations.

## 5. Teleoperation

Open **Teleoperation**, select OmniHand 2025 (O10), OmniHand 3 Ultra (T1.3 / T1.5) or OmniHand 3 Lite, and choose left, right or both hands.

- **Simulation**: connect the matching gloves and click **Start teleoperation** to open MuJoCo. No robot or separate Python installation is needed. Stopping teleoperation closes the simulation window.
- **Live device**: select the physical connection and enter the device ID, CAN channel, network or serial settings. Match each glove to the corresponding robot hand. Use separate CAN adapter channels/adapters or serial ports; a shared SocketCAN interface needs different device IDs. For first use, lower the joint speed limit in advanced settings.

The **Glove input recording and playback** panel saves current teleoperation inputs as `.ogteleop`. Open an action file to solve its inputs again and replay them in simulation or on hardware without connected gloves. Hardware playback still requires the robot connection.

## 6. Firmware Update

Stop recording, exit playback and finish other tasks. In **Firmware**, refresh devices and check the target identity and current versions. Select **Application**, **Node** or **Node + application**, choose the matching official BIN/HEX firmware, validate it, and review the target and versions before writing.

Combined updates write the node first. Once writing starts, it cannot be cancelled and the application cannot close. Keep power and USB connected. With multiple devices or DFU mode, identify the target by USB location. Device firmware images are not included in these Toolbox installation packages.

See [Troubleshooting](TROUBLESHOOTING.md) if needed.
