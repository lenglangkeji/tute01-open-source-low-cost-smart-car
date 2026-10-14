# 来源与抓取日志 · Sources and Capture Log

[中文](#中文) · [English](#english)

---

## 中文

本仓库是对公开发布网页的存档。本文件记录抓取的时间、方式与来源，便于日后审计或更新。

### 命名说明

本存档**统一使用「图特01 / Tute01」**作为项目名称。源站教学页面的原始标题使用了另一个产品名；`sources/` 中的 HTML 快照与纯文本提取均保持原样、未做改写，因此其中的原始用词可以查到。

### 抓取概况

| 项目 | 内容 |
| --- | --- |
| 抓取日期 | 2026-10-14 |
| 抓取方式 | 每个页面一次 HTTP GET，使用常规桌面浏览器 user-agent |
| 鉴权 | 无，所有页面均可公开访问 |
| 站点 | `http://www.tute01.site/`、`http://www.lenglang.xyz/` |
| 未能访问 | `www.tute01.com` 下全部主机（DNS 解析失败） |

### 已抓取页面

**tute01.site**

| 源地址 | 本地 HTML | 本地文本 | 状态 |
| --- | --- | --- | --- |
| `http://www.tute01.site/` | `sources/html/tute01.site__index.html` | `sources/text/tute01.site__index.txt` | 200 OK |

**lenglang.xyz**

| 源地址 | 本地 HTML | 本地文本 | 状态 |
| --- | --- | --- | --- |
| `http://www.lenglang.xyz/` | `sources/html/lenglang.xyz__index.html` | `sources/text/lenglang.xyz__index.txt` | 200 OK |
| `http://www.lenglang.xyz/teaching.html` | `sources/html/lenglang.xyz__teaching.html` | `sources/text/lenglang.xyz__teaching-ros2-smart-car.txt` | 200 OK |
| `http://www.lenglang.xyz/downloads.html` | `sources/html/lenglang.xyz__downloads.html` | `sources/text/lenglang.xyz__downloads.txt` | 200 OK |
| `http://www.lenglang.xyz/custom.html` | `sources/html/lenglang.xyz__custom.html` | `sources/text/lenglang.xyz__custom-development.txt` | 200 OK |
| `http://www.lenglang.xyz/consulting.html` | `sources/html/lenglang.xyz__consulting.html` | `sources/text/lenglang.xyz__consulting-competition.txt` | 200 OK |
| `http://www.lenglang.xyz/shop.html` | `sources/html/lenglang.xyz__shop.html` | `sources/text/lenglang.xyz__shop.txt` | 200 OK（第二次尝试） |

### 未能抓取

| 源地址 | 原因 |
| --- | --- |
| `http://www.tute01.com/` | DNS 解析失败 |
| `http://www.tute01.com/111.html` | DNS 解析失败（下位机代码仓库） |
| `http://www.tute01.com/456.html` | DNS 解析失败（项目教学网址） |
| `http://www.tute01.com/che.mp4` | DNS 解析失败（项目主页内嵌演示视频） |
| `tuto01.lenglang.xyz/videos` | 源页面中该链接渲染为 `href="#"` |

### 图片

所有被已抓取页面引用的图片均已下载并按原样存放在 `assets/` 下。

| 目录 | 内容 | 数量 |
| --- | --- | --- |
| `assets/smart-car/` | 来自 `tute01.site` 的底盘与产品照片 | 3 |
| `assets/studio/` | 工作室 logo、工作照、微信与抖音二维码、favicon | 6 |
| `assets/consulting/` | 来自 `lenglang.xyz/consulting.html` 的比赛指导图集 | 15 |

`tute01.site` 上引用的两张图片（`favicon.ico`、`logo_sharp.png`）返回 HTTP 404，未能存档。

> **图片未被分析、OCR、描述或以其他方式解读。** 它们按收到的原始字节保存，以保持存档可低成本复现，并避免任何二进制内容进入文本处理流程。

### 保真说明

- HTML 快照按原始字节解码为 UTF-8 文本保存，保留原始标记，包括发布方自身的笔误。
- 纯文本提取会移除 `script`、`style`、`noscript` 与 `head` 元素，折叠连续空白并删除空行，除此之外不做编辑。
- 中文文本原样保留。`README.md` 与 `docs/` 中的英文内容是为本存档编写的中英双语整理。

### 如何重新抓取

本存档可复现：按上表地址用标准 HTTP 客户端抓取，并重复 `docs/07-links-and-credits.md` 中「本存档的制作方式」的第 2、3 步。

---

## English

This repository is an archive of publicly published web pages. This file records exactly what was
captured, when, and from where, so the archive can be audited or refreshed later.

### Naming note

This archive uses **Tute01 (图特01)** as the single project name. The original teaching page used a
different product title; the HTML snapshots and plain-text extracts under `sources/` are left
untouched, so the original wording remains traceable there.

### Capture summary

| Field | Value |
| --- | --- |
| Capture date | 2026-10-14 |
| Method | Single HTTP GET per page with a conventional desktop browser user-agent |
| Auth | None — all pages are publicly accessible |
| Sites | `http://www.tute01.site/`, `http://www.lenglang.xyz/` |
| Unreachable | All hosts under `www.tute01.com` (DNS resolution failure) |

### Captured pages

**tute01.site**

| Source URL | Local HTML | Local text | Status |
| --- | --- | --- | --- |
| `http://www.tute01.site/` | `sources/html/tute01.site__index.html` | `sources/text/tute01.site__index.txt` | 200 OK |

**lenglang.xyz**

| Source URL | Local HTML | Local text | Status |
| --- | --- | --- | --- |
| `http://www.lenglang.xyz/` | `sources/html/lenglang.xyz__index.html` | `sources/text/lenglang.xyz__index.txt` | 200 OK |
| `http://www.lenglang.xyz/teaching.html` | `sources/html/lenglang.xyz__teaching.html` | `sources/text/lenglang.xyz__teaching-ros2-smart-car.txt` | 200 OK |
| `http://www.lenglang.xyz/downloads.html` | `sources/html/lenglang.xyz__downloads.html` | `sources/text/lenglang.xyz__downloads.txt` | 200 OK |
| `http://www.lenglang.xyz/custom.html` | `sources/html/lenglang.xyz__custom.html` | `sources/text/lenglang.xyz__custom-development.txt` | 200 OK |
| `http://www.lenglang.xyz/consulting.html` | `sources/html/lenglang.xyz__consulting.html` | `sources/text/lenglang.xyz__consulting-competition.txt` | 200 OK |
| `http://www.lenglang.xyz/shop.html` | `sources/html/lenglang.xyz__shop.html` | `sources/text/lenglang.xyz__shop.txt` | 200 OK (second attempt) |

### Not captured

| Source URL | Reason |
| --- | --- |
| `http://www.tute01.com/` | DNS resolution failure |
| `http://www.tute01.com/111.html` | DNS resolution failure (lower-controller/firmware repository) |
| `http://www.tute01.com/456.html` | DNS resolution failure (teaching site) |
| `http://www.tute01.com/che.mp4` | DNS resolution failure (demo video, embedded on the project site) |
| `tuto01.lenglang.xyz/videos` | Referenced link is rendered as `href="#"` on the source page |

### Images

All images referenced by the captured pages were downloaded and stored unmodified under `assets/`.

| Folder | Contents | Count |
| --- | --- | --- |
| `assets/smart-car/` | Chassis and product photos from `tute01.site` | 3 |
| `assets/studio/` | Studio logo, workshop photos, WeChat and Douyin QR codes, favicon | 6 |
| `assets/consulting/` | Competition-coaching gallery from `lenglang.xyz/consulting.html` | 15 |

Two images referenced on `tute01.site` (`favicon.ico`, `logo_sharp.png`) returned HTTP 404 and could
not be archived.

> **Images were not analysed, OCR'd, described or otherwise interpreted.** They are stored exactly
> as received to keep the archive cheap to reproduce and to avoid sending binary content through
> any text pipeline.

### Fidelity notes

- HTML snapshots are stored as decoded UTF-8 text of the original bytes, preserving the original
  markup, including the publisher own typos.
- Plain-text extractions strip `script`, `style`, `noscript` and `head` elements, collapse runs of
  whitespace, and drop blank lines. No other editing is applied.
- Chinese text is preserved verbatim. Text in `README.md` and `docs/` is a bilingual editorial
  digest prepared for this archive.

### Re-capturing

The capture is reproducible: fetch the URLs listed above with a standard HTTP client and repeat
steps 2 and 3 of the production notes in `docs/07-links-and-credits.md`.
