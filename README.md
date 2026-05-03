# 🔭 OpenSLAM
### DIY Architectural LiDAR SLAM Scanner

> Compact open-source 3D scanner for **architectural scanning** built with **Livox Mid-360** and **NanoPi Zero 2**.  
> Scan any space and get a full 3D point cloud ready for import into Share Studio.

![OpenSLAM Scanner](images/scanner_main.jpg)

📣 **Questions & support → [Telegram @a2blog](https://t.me/a2blog)**

---

## 📋 Table of Contents
- [What is this?](#-what-is-this)
- [Components](#-components)
- [3D Printed Parts](#-3d-printed-parts)
- [Assembly](#-assembly)
- [Software & Setup](#-software--setup)
- [How Scanning Works](#-how-scanning-works)

---

## 🤔 What is this?

A handheld SLAM scanner designed specifically for **architectural use** — scan rooms, buildings, and spaces, then bring the result into **Share Studio** as a point cloud.

The scanner is **open hardware**: buy the components, print the parts, assemble. For software setup you have two paths — do it yourself or contact us.

---

## 📦 Components

| # | Component | Details |
|---|-----------|---------|
| 1 | **Livox Mid-360** | Main LiDAR sensor |
| 2 | **NanoPi Zero 2** | Onboard computer |
| 3 | **Powerbank** | 10,000+ mAh recommended |
| 4 | **M3 Screws** | 8× M3×10mm |
| 5 | **3D Printed Parts** | See section below ↓ |

![Components](images/components_overview.jpg)

---

## 🖨️ 3D Printed Parts

| Part | File | Infill |
|------|------|--------|
| LiDAR Mount | [`lidar_mount.stl`](stl/lidar_mount.stl) | 30% |
| Main Body | [`main_body.stl`](stl/main_body.stl) | 25% |
| Battery Holder | [`battery_holder.stl`](stl/battery_holder.stl) | 20% |

Material: PLA or PETG · Layer height: 0.2mm · Supports: Main Body only

![Printed parts](images/printed_parts.jpg)

---

## 🔧 Assembly

[![Watch assembly on YouTube Shorts](images/thumbnail_assembly.jpg)](https://youtube.com/YOUR_ASSEMBLY_SHORTS_LINK)

> Full assembly from components shown in the Shorts above.

![Assembly step 1](images/assembly_1.jpg)
![Assembly step 2](images/assembly_2.jpg)

---

## 💻 Software & Setup

The repository includes ready-to-use software in the [`/software`](software/) folder:

| File | Description |
|------|-------------|
| `openslam.apk` | Android app — start/stop scanner, monitor status |
| `converter_v2.4.4.exe` | Converts scan output to Share Studio format (**v2.4.4**, may update) |

### Option A — Contact us for setup (recommended)

We flash the board, configure everything, and the software above works out of the box.

**→ [Write us on Telegram @a2blog](https://t.me/a2blog)**

### Option B — DIY setup

If you want to configure everything yourself, here's what needs to be done on the NanoPi Zero 2:

1. [Install ROS 2 Humble](https://docs.ros.org/en/humble/Installation.html)
2. [Install Livox SDK](https://github.com/Livox-SDK/livox_ros_driver)
3. [Install Livox ROS Driver 2](https://github.com/Livox-SDK/livox_ros_driver2)
4. Write a script for automatic scan start/stop
5. Configure and broadcast a Wi-Fi access point on the board
6. Develop a smartphone app to control start/stop over Wi-Fi
7. Develop a converter to transform scan output into a Share Studio-compatible format

> This is a non-trivial setup. If you're not sure — [just ask us](https://t.me/a2blog), it's faster.

---

## 📡 How Scanning Works

[![Watch scanning on YouTube Shorts](images/thumbnail_scanning.jpg)](https://youtube.com/YOUR_SCANNING_SHORTS_LINK)

> From power-on to finished point cloud — shown in the Shorts above.

1. Power on the scanner — it boots and broadcasts a Wi-Fi hotspot
2. Connect your phone to the hotspot and open the app
3. Press **Start** — walk through the space slowly
4. Press **Stop** — scan is saved to the device
5. Transfer the file to PC and run `converter_v2.4.4.exe`
6. Import the result into **Share Studio**

![Point cloud result](images/pointcloud_example.jpg)

---

## 📁 Repository Structure

```
OpenSLAM/
├── README.md
├── stl/
│   ├── lidar_mount.stl
│   ├── main_body.stl
│   └── battery_holder.stl
├── software/
│   ├── openslam.apk
│   └── converter_v2.4.4.exe
└── images/
```

---

## 📄 License

MIT License — free to use, modify, and share. See [`LICENSE`](LICENSE).

---

## 💬 Contact

**[Telegram @a2blog](https://t.me/a2blog)** — questions, setup requests, feedback.  
If this helped you, give the repo a ⭐
