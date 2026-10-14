# Tute01 开源智能车 · Tute01 Open-Source Smart Car

**≈ 50 美元的低成本 ROS 2 学习小车 · A ≈ US$50 low-cost ROS 2 learning car**

> 中英双语整理存档 · Bilingual Chinese/English archive
> 来源 / Sources: <http://www.tute01.site/> · <http://www.lenglang.xyz/>

[中文](#中文) · [English](#english)

---

## 中文

### 这是什么

**图特01（Tute01）** 是一台**约 50 美元（350 元）的低成本 ROS 2 学习小车**，也是一个超低成本的智能驾驶开源平台：
面向预算有限、希望用真实底盘学习导航、SLAM 与传感器驱动的学生与爱好者。

项目由**冷狼科技团队**（冷狼科技 / 冷狼电子工作室）发布，团队由天津多所理工及师范类院校的研究生与本科生组建。

> 本仓库是对 `tute01.site` 与 `lenglang.xyz` 公开发布内容的**中英双语整理与存档**。所有原始中文文本均原样保留在 [`sources/`](sources/) 目录下；图片按原样保存，**不做识别、OCR 或描述**。

### 项目定位

项目主页提出的两句话：

> 让教育尽可能普及，不受限于资源
> 让开源尽可能实用，不拘泥于高端

英文标语：*Open · Innovative · Exploring the Infinite Possibilities of Autonomous Driving*

项目主页同时给出如下自述：*“Tuto01 Smart Car is a comprehensive open-source autonomous driving platform designed for learning machine vision, artificial intelligence, and control algorithms. Based on a powerful microcontroller and an HD camera, it enables object detection, visual tracking, and automatic obstacle avoidance.”*

### 项目一览

| 项目 | 说明 |
| --- | --- |
| 名称 | 图特01（Tute01） |
| 类别 | 开源智能车、ROS 2 训练底盘 |
| 入门成本 | 低至约 350 元（约 50 美元） |
| 上位机 | 树莓派（Ubuntu 22.04 + ROS 2 Humble） |
| 主控 | STM32（micro-ROS / 串口与 ROS 2 通信） |
| 传感器 | 激光雷达、IMU、编码器里程计、高清摄像头 |
| 软件栈 | ROS 2 Humble、Nav2、SLAM Toolbox、Gazebo |
| 团队 | 冷狼科技团队（天津） |
| 许可 | 原始发布方未声明 |

### 核心思路

项目主页的核心主张是：把底盘做得**足够便宜、易于复现，同时体积大、承载能力强**，让初学者能快速把一台能跑的车放到地上。教学页面把该产品描述为一款开源智能车训练底盘：基于 ROS 2 开发，适合学习机器人导航、SLAM 建图与传感器驱动等核心技术；采用 STM32 主控加树莓派上位机，搭载激光雷达、IMU 与编码器里程计，支持 ROS 2 Humble。

### 仓库结构

```
.
├── README.md                  本文件（中英双语）
├── SOURCES.md                 抓取日志与来源说明
├── docs/
│   ├── 01-overview.md         项目背景与定位
│   ├── 02-hardware.md         底盘、电子与传感器
│   ├── 03-ros2-quickstart.md  ROS 2 Humble 指令速查
│   ├── 04-resources-and-downloads.md  固件、BOM 与下载
│   ├── 05-team.md             项目团队与学术指导
│   ├── 06-studio-and-services.md  冷狼电子工作室与其业务
│   └── 07-links-and-credits.md    链接、媒体与版权
├── assets/
│   ├── smart-car/             产品与底盘照片
│   ├── studio/                工作室 logo、工作照、联系二维码
│   └── consulting/            比赛指导图集
└── sources/
    ├── html/                  各页面的原始 HTML 快照
    └── text/                  同一批页面的纯文本提取
```

### 快速开始（ROS 2 Humble + Ubuntu 22.04）

```bash
# 1. 依赖
sudo apt update
sudo apt install ros-humble-desktop ros-humble-gazebo-ros-pkgs \
                 ros-humble-navigation2 ros-humble-slam-toolbox

# 2. 工作空间
mkdir -p ~/tute01_ws/src && cd ~/tute01_ws
colcon build && source install/setup.bash

# 3. 底盘控制
ros2 topic pub /cmd_vel geometry_msgs/msg/Twist \
  "{linear: {x: 0.5, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}" -1

# 4. 读取传感器
ros2 topic echo /scan   # 激光雷达
ros2 topic echo /imu    # IMU 姿态
ros2 topic echo /odom   # 里程计

# 5. SLAM 与导航
ros2 launch slam_toolbox online_async_launch.py
ros2 run nav2_map_server map_saver_cli -f ~/map
ros2 launch nav2_bringup bringup_launch.py map:=~/map.yaml

# 6. Gazebo 仿真
ros2 launch tute01_gazebo tute01_world.launch.py
```

带注释的版本见 [`docs/03-ros2-quickstart.md`](docs/03-ros2-quickstart.md)。

### 官方链接

| 资源 | 链接 |
| --- | --- |
| 项目站点 | <http://www.tute01.site/> |
| 工作室站点 | <http://www.lenglang.xyz/> |
| ROS 2 教学系列 | <http://www.lenglang.xyz/teaching.html> |
| 视频教程（B 站） | <https://www.bilibili.com/video/BV1N3zYBaEkZ/> |
| BOM 表下载 | <https://wwbxu.lanzouv.com/i2khA3flupej>（提取码 `hm2w`） |
| 智能车源码包 | <https://wwd.lanzoub.com/inF8406oa1wj> |

### 范围与免责声明

- 本仓库是对公开网页内容的**整理与保存**，不是官方发布渠道，与原始发布方无隶属关系。
- **图片内容未被识别、OCR 或描述**，均按下载时的原始字节保存，以便存档可低成本复现。
- 源站文本为简体中文，已在 `sources/` 中原样保留；`docs/` 与英文部分为供存档使用的翻译与摘要。
- 本存档统一使用「图特01 / Tute01」作为项目名称；原始快照保持原样，详见 [`SOURCES.md`](SOURCES.md)。
- 第三方下载链接（蓝奏云、B 站、CSDN）由各自运营方提供服务，可能失效。
- 如您是权利方并希望删除或更正内容，请提交 issue。

---

## English

### What this is

**Tute01** (图特01) is a **≈ US$50 (CNY 350) low-cost ROS 2 learning car** and an ultra-low-cost
open-source autonomous-driving platform. It targets students and hobbyists who want a real robot
chassis to study navigation, SLAM and sensor drivers without a large budget.

The project is published by the **Lenglang Tech Team** (Lenglang Electronics Studio), a group of
graduate and undergraduate students from several engineering and normal universities in Tianjin,
China.

> This repository is a **bilingual archive** of the public material published on `tute01.site` and
> `lenglang.xyz`. All original Chinese text is preserved verbatim under [`sources/`](sources/).
> Images are stored as-is and are **not** recognised, OCR'd or described.

### Positioning and motto

The project site leads with a two-line mission statement:

> Make education as accessible as possible, not limited by resources.
> Make open source as practical as possible, not bound to high-end hardware.

The English tagline on the same page is *Open · Innovative · Exploring the Infinite Possibilities
of Autonomous Driving*, and the platform self-description reads:

> *"Tuto01 Smart Car is a comprehensive open-source autonomous driving platform designed for
> learning machine vision, artificial intelligence, and control algorithms. Based on a powerful
> microcontroller and an HD camera, it enables object detection, visual tracking, and automatic
> obstacle avoidance."*

### At a glance

| Item | Detail |
| --- | --- |
| Project name | Tute01 (图特01) |
| Category | Open-source smart car, ROS 2 training chassis |
| Entry cost | From ~350 CNY (≈ US$50) |
| Host computer | Raspberry Pi (Ubuntu 22.04, ROS 2 Humble) |
| Main controller | STM32 (micro-ROS / serial link to ROS 2) |
| Sensors | 2D LiDAR, IMU, wheel-encoder odometry, HD camera |
| Software stack | ROS 2 Humble, Nav2, SLAM Toolbox, Gazebo |
| Team | Lenglang Tech Team, Tianjin, China |
| License | Not stated by the original publisher |

### Core idea

The premise is a chassis that is **cheap to build, easy to reproduce, and still large with high
load capacity**, so beginners can get a working robot on the floor quickly. The teaching page
describes the product as an open-source smart-car training chassis developed on ROS 2, suited to
learning robot navigation, SLAM mapping and sensor drivers, using an STM32 main controller plus a
Raspberry Pi host computer, carrying a LiDAR, an IMU and encoder odometry, and supporting ROS 2
Humble.

### Repository layout

```
.
├── README.md                  this file (bilingual)
├── SOURCES.md                 capture log and provenance
├── docs/                      bilingual document set
├── assets/                    images, stored unmodified
└── sources/                   raw HTML snapshots and plain-text extracts
```

### Quick start

The command sequence is identical to the Chinese section above; the annotated bilingual version is
in [`docs/03-ros2-quickstart.md`](docs/03-ros2-quickstart.md).

### Official links

| Resource | Link |
| --- | --- |
| Project site | <http://www.tute01.site/> |
| Studio site | <http://www.lenglang.xyz/> |
| ROS 2 teaching series | <http://www.lenglang.xyz/teaching.html> |
| Video tutorial (Bilibili) | <https://www.bilibili.com/video/BV1N3zYBaEkZ/> |
| BOM download | <https://wwbxu.lanzouv.com/i2khA3flupej> (access code `hm2w`) |
| Smart-car source package | <https://wwd.lanzoub.com/inF8406oa1wj> |

### Scope and disclaimer

- This repository is an **organise-and-save archive** of publicly published web pages. It is not an
  official release channel and is not affiliated with the original publisher.
- **No image content was recognised, OCR'd or described**; images are stored byte-for-byte as
  downloaded so the archive stays inexpensive to reproduce.
- Source pages are in Simplified Chinese and are reproduced unchanged in `sources/`. The English
  text is a translation and digest prepared for this archive.
- This archive uses **Tute01 (图特01)** as the single project name throughout; original snapshots
  are left untouched — see [`SOURCES.md`](SOURCES.md).
- Third-party download links (Lanzou, Bilibili, CSDN) are operated by their respective owners and
  may expire.
- If you are the rights holder and want content removed or corrected, please open an issue.
