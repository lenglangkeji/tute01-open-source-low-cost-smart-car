# 机械 CAD · Mechanical CAD

[中文](#中文) · [English](#english)

---

## 中文

本目录收录 Tute01 智能车的**机械 CAD 源文件**（SolidWorks 装配体），由项目方提供。

### 文件清单

| 文件 | 类型 | 说明 |
| --- | --- | --- |
| `cad/装配体1.SLDASM` | 装配体 | 整车总装配 |
| `cad/零件1.SLDPRT` … `cad/零件11.SLDPRT` | 零件 | 车体结构件 |
| `cad/零件5(2).SLDPRT` | 零件 | 零件 5 的另一个版本 |
| `cad/Mirror零件3/4/6/7/8.SLDPRT` | 零件 | 镜像件 |

共 1 个装配体 + 17 个零件，合计约 2.3 MB。

### 如何打开

- **SolidWorks**：直接打开 `cad/装配体1.SLDASM`；建议同时保留同目录下的零件文件，否则会提示找不到参考。
- **无 SolidWorks**：可用免费查看器 **eDrawings Viewer**，或任意支持 SolidWorks 文件的在线查看器浏览。
- 文件为 SolidWorks 原生二进制格式，**不是** STEP/STL 等中间格式；如需跨软件使用，请在 SolidWorks 中另存为 STEP。

### 说明

- 文件名保留原始中文命名（零件 / 镜像零件 / 装配体）。
- 仓库不包含渲染图，因为 SolidWorks 私有格式无法在本环境中自动导出预览。若需预览图，请在 SolidWorks 中截图或导出 PNG 后补充。

---

## English

This folder holds the **mechanical CAD source files** (SolidWorks assembly) of the Tute01 smart
car, provided by the project team.

### Contents

| File | Type | Notes |
| --- | --- | --- |
| `cad/装配体1.SLDASM` | Assembly | Full vehicle assembly |
| `cad/零件1.SLDPRT` … `cad/零件11.SLDPRT` | Part | Structural parts |
| `cad/零件5(2).SLDPRT` | Part | Alternate revision of part 5 |
| `cad/Mirror零件3/4/6/7/8.SLDPRT` | Part | Mirrored parts |

One assembly plus 17 parts, roughly 2.3 MB in total.

### Opening the files

- **SolidWorks** — open `cad/装配体1.SLDASM` directly. Keep the part files in the same folder or
  SolidWorks will report missing references.
- **Without SolidWorks** — use the free **eDrawings Viewer**, or any online viewer that supports
  SolidWorks files.
- These are native SolidWorks binaries, **not** STEP/STL. Export to STEP from SolidWorks if you need
  to use them in other CAD packages.

### Notes

- Original Chinese file names are preserved (零件 = part, 镜像零件 = mirrored part, 装配体 = assembly).
- No rendered previews are included, because the native SolidWorks container cannot be exported to
  an image in this environment. Add screenshots or PNG exports from SolidWorks if previews are wanted.
