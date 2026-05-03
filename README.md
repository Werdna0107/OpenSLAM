# 🔭 OpenSLAM
### DIY Architectural LiDAR SLAM Scanner

> Compact open-source 3D scanner for **architectural scanning** built with **Livox Mid-360** and **NanoPi Zero 2**.  
> Scan any space and get a full 3D point cloud ready for import into Share Studio.

![OpenSLAM Scanner](images/b8a8bbff-2bd7-42a2-ba9b-e9cb7aeee88f.jpg)

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

### 🔩 Electronics

| # | Component | Details |
|---|-----------|---------|
| 1 | **Livox Mid-360** | Main LiDAR sensor. Mid-360S also supported |
| 2 | **NanoPi Zero 2** | Must have **Wi-Fi module** and **eMMC storage** |
| 3 | **Powerbank** | 2 outputs required: one 10W+, one with **12V or 20V PD output**. Tested on **HPS99** — works great. HPS36 and Vectorgear should also work (lighter, but untested) |

### 🔌 Cables

| # | Component | Details |
|---|-----------|---------|
| 4 | **NanoPi power cable** | Min. 15cm, USB-C on board side. Second end depends on powerbank: USB-C for HPS99, USB-A for Vectorgear |
| 5 | **LiDAR cable** | Connects LiDAR to board and power. Two options: **rigid** (0.5m, more durable) or **flexible** (0.2m, less bulk but less durable) |
| 6 | **USB-C PD trigger** | 12V or 20V, soldered to the LiDAR power end. *If you contact us for setup, we solder this for you when you provide the components* |

### 🔧 Fasteners

| # | Component | Qty |
|---|-----------|-----|
| 7 | **M3×8 screws** | 4× — LiDAR to body |
| 8 | **M2.5×12 screws** | 4× — NanoPi to body |
| 9 | **1/4" flat nut** | 1× — handle attachment to body |
| 10 | **1/4" bolt** | 1× — stand attachment to powerbank |

### 🖨️ 3D Printed Parts

| # | Part | Purpose |
|---|------|---------|
| 11 | **Body** | Main frame — LiDAR, NanoPi and powerbank all mount to this |
| 12 | **LiDAR guard** | Protects the fragile sensor part from drops |
| 13 | **Battery stand** | Keeps the scanner stable when set down |

> See STL files and print settings in the [3D Printed Parts](#%EF%B8%8F-3d-printed-parts) section below ↓

---

> 💬 **Not sure which components to pick?** Ask in our chat — **[t.me/a2blogchat](https://t.me/a2blogchat)**
> 
> 📐 **Need a custom form factor** with this same architecture? We can design it — [write us](https://t.me/a2blogchat)

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
