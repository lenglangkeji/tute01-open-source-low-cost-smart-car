# 02 — 硬件 · Hardware

[中文](#中文) · [English](#english)

---

## 中文

### 设计理念

Tute01 底盘由三个公开特征定义：

1. **超低成本** —— 项目主页宣传其硬件方案低至 **350 元**。
2. **大体积、高承载** —— 底盘尺寸大，可搭载额外负载。
3. **易于搭建** —— 让初学者也能组装与复现。

其目标用户是预算有限、刚开始接触智能驾驶、路径规划与 ROS 2 的学习者。

### 子系统构成

| 层次 | 部件 | 说明 |
| --- | --- | --- |
| 上位机 | 树莓派 | 运行 Ubuntu 22.04 与 ROS 2 Humble |
| 主控 | STM32 | 下层控制器，负责电机与 I/O |
| 测距 | 激光雷达 | 发布 `/scan` |
| 姿态 | IMU | 发布 `/imu` |
| 里程 | 编码器 | 发布 `/odom` |
| 视觉 | 高清摄像头 | 用于检测、跟踪与避障 |
| 中间件 | ROS 2 Humble | Navigation2、SLAM Toolbox、Gazebo |

教学页面对该产品的描述是：它是一款开源智能车训练底盘，基于 ROS 2 开发，适合学习机器人导航、SLAM 建图与传感器驱动等核心技术；采用 STM32 主控加树莓派上位机，搭载激光雷达、IMU 与编码器里程计，支持 ROS 2 Humble。

### 上位机与主控的通信

教学页面的推荐阅读中包含《树莓派 + Micro-ROS 环境搭建》，其描述是**实现 STM32 与 ROS2 的串口通信**。这是文档中给出的“下层控制器 ↔ ROS 2 上位机”桥接方案。

### 电机与驱动

发布方并未在本次抓取到的网页上给出详细的电机/物料清单，而是**以可下载的 BOM 表格分发**：

- BOM 下载：<https://wwbxu.lanzouv.com/i2khA3flupej> —— 提取码 `hm2w`

教学页面还链接了*小车底盘搭建教学*视频，项目主页内嵌了演示视频 `tute01.com/che.mp4`。

> BOM 本身为第三方托管文件，**本仓库不做镜像**。底盘装配步骤以视频形式提供，而非文字。

### 图片

产品与底盘照片位于 `../assets/smart-car/`（`tute01_che1.jpg`、`tute01_che2.jpg`、`tute01_che3.jpg`），按下载原样保存，本文不做描述。

### 机械 CAD

整车机械结构以 **SolidWorks 装配体**形式提供，位于 `../hardware/cad/`：1 个总装配（`装配体1.SLDASM`）
加 17 个零件（`零件1`–`零件11`、`零件5(2)` 以及 `Mirror零件3/4/6/7/8`）。打开方式与注意事项见
[`../hardware/README.md`](../hardware/README.md)。

返回 [README](../README.md)。

---

## English

### Concept

The Tute01 chassis is defined by three published characteristics:

1. **Ultra-low cost** — the project page advertises a hardware solution as cheap as **350 CNY**.
2. **Large volume and high load capacity** — a big chassis that can carry additional payloads.
3. **Easy to build** — designed so that beginners can assemble and reproduce it.

The stated audience is learners on a limited budget who are starting out in autonomous driving,
path planning and ROS 2.

### Subsystems

| Layer | Component | Notes |
| --- | --- | --- |
| Host computer | Raspberry Pi | Runs Ubuntu 22.04 with ROS 2 Humble |
| Main controller | STM32 | Lower-level controller for motors and I/O |
| Ranging | 2D LiDAR | Publishes `/scan` |
| Attitude | IMU | Publishes `/imu` |
| Odometry | Wheel encoders | Publishes `/odom` |
| Vision | HD camera | Used for detection, tracking and obstacle avoidance |
| Middleware | ROS 2 Humble | Navigation2, SLAM Toolbox, Gazebo |

The teaching page describes the product as an open-source smart-car training chassis developed on
ROS 2, suited to learning core techniques such as robot navigation, SLAM mapping and sensor
drivers. It uses an STM32 as the main controller together with a Raspberry Pi as the host computer,
and carries a LiDAR, an IMU and encoder odometry. It supports ROS 2 Humble.

### Host-to-controller link

The recommended reading list on the teaching page includes *Raspberry Pi + micro-ROS environment
setup*, described as **implementing serial communication between the STM32 and ROS 2**. That is the
documented bridge between the lower-level controller and the ROS 2 host.

### Motors and drive

The publisher does not publish a detailed motor/BOM table on the website pages captured here.
Instead, the **BOM is distributed as a downloadable spreadsheet**:

- BOM download: <https://wwbxu.lanzouv.com/i2khA3flupej> — access code `hm2w`

The teaching page also links a *chassis assembly tutorial* video, and the project page embeds a
demo video at `tute01.com/che.mp4`.

> The BOM itself is a third-party hosted archive and is **not mirrored in this repository**.
> Chassis assembly steps are delivered as video rather than as text.

### Mechanical CAD

The vehicle structure is provided as a **SolidWorks assembly** under `../hardware/cad/`: one
assembly (`装配体1.SLDASM`) plus 17 parts (`零件1`–`零件11`, `零件5(2)`, and `Mirror零件3/4/6/7/8`).
See [`../hardware/README.md`](../hardware/README.md) for how to open them.

### Photos

Product and chassis photos live in `../assets/smart-car/` (`tute01_che1.jpg`, `tute01_che2.jpg`,
`tute01_che3.jpg`). They are stored exactly as downloaded and are not described here.

Back to [README](../README.md).
