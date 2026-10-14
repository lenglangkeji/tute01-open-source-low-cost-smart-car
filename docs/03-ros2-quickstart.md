# 03 — ROS 2 快速上手 · ROS 2 Quick Start

[中文](#中文) · [English](#english)

---

## 中文

本文是冷狼电子工作室教学页面所发布 ROS 2 指令教程的整理版本，环境为 **Ubuntu 22.04 + ROS 2 Humble**。

### 1. 开发环境配置

```bash
sudo apt update
sudo apt install ros-humble-desktop
sudo apt install ros-humble-gazebo-ros-pkgs
sudo apt install ros-humble-navigation2
sudo apt install ros-humble-slam-toolbox
```

安装 ROS 2 Humble 桌面版，以及 Gazebo 集成、Navigation2 与 SLAM Toolbox。

### 2. 创建工作空间

```bash
mkdir -p ~/tute01_ws/src
cd ~/tute01_ws
colcon build
source install/setup.bash
```

工作空间名为 `tute01_ws`，与项目名一致。

### 3. 底盘基础控制

```bash
# 前进 0.5m/s
ros2 topic pub /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.5, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}" -1

# 原地左转
ros2 topic pub /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.5}}" -1
```

通过标准话题 `/cmd_vel` 发布速度指令。

### 4. 传感器数据读取

```bash
ros2 topic echo /scan   # 激光雷达
ros2 topic echo /imu    # IMU 姿态
ros2 topic echo /odom   # 里程计
```

### 5. SLAM 建图

```bash
ros2 launch slam_toolbox online_async_launch.py
ros2 run nav2_map_server map_saver_cli -f ~/map
```

使用 SLAM Toolbox 进行在线异步建图，并把地图保存到 `~/map`。

### 6. Navigation2 自主导航

```bash
ros2 launch nav2_bringup bringup_launch.py map:=~/map.yaml
```

在 RViz2 里用 **2D Goal Pose** 设定目标点，小车会自行规划路径。

### 7. Gazebo 仿真

```bash
ros2 launch tute01_gazebo tute01_world.launch.py
```

启动项目仿真包 `tute01_gazebo`。

### 推荐阅读（CSDN）

教学页面列出五篇中文文章。由于源页面的链接指向 `blog.csdn.net` 首页而非具体文章地址，此处仅保留标题：

| 序号 | 标题 | 内容要点 |
| --- | --- | --- |
| 1 | ROS2 Humble 安装教程（Ubuntu 22.04） | 手把手图解安装 ROS 2，含常见报错解决 |
| 2 | ROS2 话题通信入门（Topic / Publisher / Subscriber） | Python + C++ 双版本代码演示 |
| 3 | ROS2 Service 与 Action 详解 | 搞懂同步/异步通信机制 |
| 4 | ROS2 Launch 文件编写指南 | 从单节点到多节点编排 |
| 5 | 树莓派 + Micro-ROS 环境搭建 | 实现 STM32 与 ROS2 的串口通信 |

返回 [README](../README.md)。

---

## English

This is the English version of the ROS 2 command reference published on the Lenglang studio
teaching page. The original states that it was written by Lenglang Electronics Studio for
**Ubuntu 22.04 + ROS 2 Humble**.

### 1. Development environment

```bash
sudo apt update
sudo apt install ros-humble-desktop
sudo apt install ros-humble-gazebo-ros-pkgs
sudo apt install ros-humble-navigation2
sudo apt install ros-humble-slam-toolbox
```

Installs the ROS 2 Humble desktop stack plus Gazebo integration, Navigation2 and SLAM Toolbox.

### 2. Create a workspace

```bash
mkdir -p ~/tute01_ws/src
cd ~/tute01_ws
colcon build
source install/setup.bash
```

The workspace is named `tute01_ws`, matching the project name.

### 3. Basic chassis control

```bash
# Forward at 0.5 m/s
ros2 topic pub /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.5, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.0}}" -1

# Rotate in place to the left
ros2 topic pub /cmd_vel geometry_msgs/msg/Twist "{linear: {x: 0.0, y: 0.0, z: 0.0}, angular: {x: 0.0, y: 0.0, z: 0.5}}" -1
```

Publishes twist commands on the standard `/cmd_vel` topic.

### 4. Reading sensor data

```bash
ros2 topic echo /scan   # 2D LiDAR
ros2 topic echo /imu    # IMU attitude
ros2 topic echo /odom   # wheel odometry
```

### 5. SLAM mapping

```bash
ros2 launch slam_toolbox online_async_launch.py
ros2 run nav2_map_server map_saver_cli -f ~/map
```

Runs online asynchronous SLAM with SLAM Toolbox and saves the resulting map to `~/map`.

### 6. Navigation2 autonomous navigation

```bash
ros2 launch nav2_bringup bringup_launch.py map:=~/map.yaml
```

In RViz2, set a goal with **2D Goal Pose** and the car plans its own path.

### 7. Gazebo simulation

```bash
ros2 launch tute01_gazebo tute01_world.launch.py
```

Launches the project simulation package `tute01_gazebo`.

### Recommended reading (CSDN)

The teaching page lists five Chinese-language CSDN articles. The source page links them to the
general `blog.csdn.net` home page rather than to individual article URLs, so only the titles are
reproduced here. See the Chinese section for the titles and their content summaries.

Back to [README](../README.md).
