# 01 — 项目概览 · Project Overview

[中文](#中文) · [English](#english)

---

## 中文

### 项目是什么

图特01（Tute01）是一台**约 50 美元（350 元）的低成本 ROS 2 学习小车**，也是一个面向学习的开源智能驾驶平台。
它要做到*超低成本*，同时**体积大、承载能力强**、易于制作与复现。

它面向希望学习以下内容的人群：

- 智能驾驶基础
- 路径规划
- ROS 2（从零基础到进阶）
- 机器视觉与控制算法
- SLAM 建图与传感器驱动

### 定位与标语

项目主页用两句话表达其立场：

> 让教育尽可能普及，不受限于资源
> 让开源尽可能实用，不拘泥于高端

同一页面的英文标语为：

> *Open · Innovative · Exploring the Infinite Possibilities of Autonomous Driving*

### 发布方给出的平台描述

> *“Tuto01 Smart Car is a comprehensive open-source autonomous driving platform designed for
> learning machine vision, artificial intelligence, and control algorithms. Based on a powerful
> microcontroller and an HD camera, it enables object detection, visual tracking, and automatic
> obstacle avoidance.”*

项目主页标注的技术标签为：**ROS 2**、**Arduino**、**SLAM**。

### 背后团队

项目由**冷狼科技团队**（冷狼科技 / 冷狼电子工作室）开发，团队自述由天津多所理工及师范类院校的研究生与本科生组建，专注非标嵌入式开发、智能车教具研发与各类非标产品定制。详见 [`05-team.md`](05-team.md)。

### 两个站点的关系

| 站点 | 作用 |
| --- | --- |
| `tute01.site` | Tute01 开源智能车的**项目主页**：定位、团队、资源与演示视频。 |
| `lenglang.xyz` | **冷狼电子工作室官网**。其 ROS2 教学板块承载 Tute01 开源智能车课程与 ROS 2 指令教程。 |

项目主页把工作室站点列为其*官方网站*，把 `tute01.com/456.html` 列为其*教学网址*。工作室教学板块同样以 Tute01 之名介绍这款开源智能车，其中的 ROS 2 指令教程使用的正是本项目的工作空间名 `tute01_ws`，仿真包名为 `tute01_gazebo`。

> 命名说明：本存档统一使用「图特01 / Tute01」。源站教学页面的原始标题与此不同，`sources/` 中的快照保持原样，详见 [`SOURCES.md`](../SOURCES.md)。

### 本存档包含什么

- `docs/` 下每个页面的中英双语整理。
- `sources/` 下原始 HTML 的逐字节副本与纯文本提取。
- `assets/` 下全部引用图片，未经修改。

返回 [README](../README.md)。

---

## English

### What the project is

The Tute01 smart car is a **≈ US$50 (CNY 350) low-cost ROS 2 learning car** and an open-source
autonomous-driving platform built for learning. It aims to be *ultra-low-cost* while still offering
a **large chassis with high load capacity** that is easy to build and reproduce.

It is aimed at people who want to study:

- autonomous-driving fundamentals,
- path planning,
- ROS 2, from beginner level upwards,
- machine vision and control algorithms,
- SLAM mapping and sensor drivers.

### Positioning and motto

The project site leads with a two-line mission statement:

> 让教育尽可能普及，不受限于资源
> 让开源尽可能实用，不拘泥于高端

Rendered in English for this archive:

> Make education as accessible as possible, not limited by resources.
> Make open source as practical as possible, not bound to high-end hardware.

The English tagline shown on the same page is:

> *Open · Innovative · Exploring the Infinite Possibilities of Autonomous Driving*

### Platform summary, as described by the publisher

> *"Tuto01 Smart Car is a comprehensive open-source autonomous driving platform designed for
> learning machine vision, artificial intelligence, and control algorithms. Based on a powerful
> microcontroller and an HD camera, it enables object detection, visual tracking, and automatic
> obstacle avoidance."*

Topic tags advertised on the project page: **ROS 2**, **Arduino**, **SLAM**.

### Who is behind it

The project is developed by the **Lenglang Tech Team** (冷狼科技 / 冷狼电子工作室), described as a
team of graduate and undergraduate students from a number of science-and-engineering and normal
universities in Tianjin. The team states that it focuses on non-standard embedded development,
smart-car teaching products and custom hardware. See [`05-team.md`](05-team.md).

### Relationship between the two sites

| Site | Role |
| --- | --- |
| `tute01.site` | The **project landing page** for the Tute01 open-source smart car: positioning, team, resources and demo video. |
| `lenglang.xyz` | The **studio website** of Lenglang Electronics Studio. Its ROS 2 teaching section hosts the Tute01 open-source smart-car course and the ROS 2 command tutorials. |

The project page links to the studio site as its *official website*, and to `tute01.com/456.html`
as its *teaching site*. The studio teaching section covers the same open-source smart car under the
Tute01 name, and its ROS 2 command reference uses this project workspace name, `tute01_ws`, with
the simulation package named `tute01_gazebo`.

> Naming note: this archive uses **Tute01 (图特01)** as the single project name. The original
> teaching page used a different product title; snapshots under `sources/` are left untouched — see
> [`SOURCES.md`](../SOURCES.md).

### What this archive contains

- Bilingual (Chinese/English) digests of every captured page, in `docs/`.
- Byte-for-byte copies of the original HTML plus a plain-text extraction, in `sources/`.
- All referenced images, stored unmodified, in `assets/`.

Back to [README](../README.md).
