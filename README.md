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

## 💡 What is this?

A handheld SLAM scanner designed for architects and surveyors — capture spatial datasets and convert them for use in **Share Studio**, where point clouds are generated and processed.

The scanner is **open hardware**: source the components, 3D-print the parts, and assemble it yourself. For software, you can either handle the dataset conversion workflow on your own or contact us for setup and support.


---

## 📦 Components

<table>
  <tr>
    <td align="center" valign="top"><img src="images/resized-1.jpg" width="300"/><br/><br/><b>1. Livox Mid-360</b><br/>Main LiDAR sensor. Mid-360S also supported</td>
    <td align="center" valign="top"><img src="images/resized-2.jpg" width="300"/><br/><br/><b>2. NanoPi Zero 2</b><br/>Must have Wi-Fi module and eMMC storage</td>
    <td align="center" valign="top"><img src="images/resized-3.jpg" width="300"/><br/><br/><b>3. Powerbank</b><br/>2 outputs required: one 10W+, one with 12V or 20V PD output.<br/>Tested: <b>HPS99</b> ✅ · HPS36 and Vectorgear should work (lighter, untested)</td>
  </tr>
  <tr>
    <td align="center" valign="top"><img src="images/resized-4.jpg" width="300"/><br/><br/><b>4. LiDAR cable + USB-C PD trigger</b><br/>Rigid 0.5m (durable) or flexible 0.2m (compact).<br/>USB-C PD trigger 12V or 20V — soldered to power end</td>
    <td align="center" valign="top"><img src="images/resized-5.jpg" width="300"/><br/><br/><b>5. Fasteners</b><br/>M3×8 × 4pcs — lidar to body<br/>M2.5×12 × 4pcs — NanoPi to body<br/>1/4" flat nut × 1 — handle to body<br/>1/4" bolt × 1 — stand to powerbank</td>
    <td align="center" valign="top"><img src="images/resized-6.jpg" width="300"/><br/><br/><b>6. 3D Printed Parts</b><br/>head · lidar guard · battery stand<br/>See <a href="#%EF%B8%8F-3d-printed-parts">3D Printed Parts</a> section ↓</td>
  </tr>
</table>

> 💬 **Not sure which components to pick?** Ask in our chat — **[t.me/a2blogchat](https://t.me/a2blogchat)**
> 
> 📐 **Need a custom form factor** with this same architecture? We can design it — [write us](https://t.me/a2blogchat)

---

## 🖨️ 3D Printed Parts

| Part | File | Infill |
|------|------|--------|
| Body | [`head.stl`](stl/head.stl) | 25% |
| LiDAR guard | [`guard.stl`](stl/guard.stl) | 20% |
| Battery stand | [`stand.stl`](stl/stand.stl) | 20% |

Material: PLA or PETG · Layer height: 0.2mm · Supports: Body only

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
