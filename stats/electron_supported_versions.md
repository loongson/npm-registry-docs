# LoongArch Electron 版本清单
---

- 共 22 个版本 · 最后检测：2026-11-05 16:54:51（北京时间）

## 快速查找

| ABI | 版本数 | 最新版本 | 安装镜像（ELECTRON_MIRROR） |
| --- | -----: | -------- | --------------------------- |
| [ABI2.0](#abi20) | 9 | v34.3.4 | `https://github.com/loongson/electron/releases/download/` |
| [ABI1.0](#abi10) | 16 | v31.7.7 | `https://ftp.loongnix.cn/electron/LoongArch/` |
| [ABI1.0 LSX 优化版](#abi10) | 2 | v31.7.7 | `https://ftp.loongnix.cn/electron/LoongArch/electron-lsx/` |

> 说明：ABI1.0 与 ABI2.0 的二进制包互不兼容，安装前请先用 `LC_ALL=C readelf -h /bin/bash | grep Flags:` 确认系统 ABI，输出 `0x3` 为 ABI1.0、`0x43` 为 ABI2.0。

<a id="abi20"></a>

## ABI2.0
> 9 个版本 · 最新 v34.3.4（2025-03-20）

| 版本号 | 网站发布时间 | 下载地址 |
| ------ | ------------ | -------- |
| v34.3.4 | 2025-03-20 | [下载](https://github.com/loongson/electron/releases/tag/v34.3.4) |
| v33.4.6 | 2025-03-20 | [下载](https://github.com/loongson/electron/releases/tag/v33.4.6) |
| v32.3.3 | 2025-03-20 | [下载](https://github.com/loongson/electron/releases/tag/v32.3.3) |
| v31.7.7 | 2025-03-20 | [下载](https://github.com/loongson/electron/releases/tag/v31.7.7) |
| v30.5.1 | 2025-02-26 | [下载](https://github.com/loongson/electron/releases/tag/v30.5.1) |
| v29.4.6 | 2025-02-26 | [下载](https://github.com/loongson/electron/releases/tag/v29.4.6) |
| v28.3.3 | 2025-02-26 | [下载](https://github.com/loongson/electron/releases/tag/v28.3.3) |
| v27.3.11 | 2025-02-26 | [下载](https://github.com/loongson/electron/releases/tag/v27.3.11) |
| v26.6.10 | 2025-02-26 | [下载](https://github.com/loongson/electron/releases/tag/v26.6.10) |

<a id="abi10"></a>

## ABI1.0
> 16 个版本 + 2 个 LSX 优化版 · 最新 v31.7.7（2025-03-07）

| 版本号 | 网站发布时间 | 类型 | 下载地址 |
| ------ | ------------ | ---- | -------- |
| v31.7.7 | 2025-03-07 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v31.7.7/) |
| v31.7.7 | 2026-06-24 | [LSX 优化版](#lsx-优化版说明) | [下载](https://ftp.loongnix.cn/electron/LoongArch/electron-lsx/v31.7.7/) |
| v30.5.1 | 2025-03-07 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v30.5.1/) |
| v28.3.3 | 2025-03-07 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v28.3.3/) |
| v28.3.3 | 2026-06-24 | [LSX 优化版](#lsx-优化版说明) | [下载](https://ftp.loongnix.cn/electron/LoongArch/electron-lsx/v28.3.3/) |
| v26.4.3 | 2023-12-18 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v26.4.3/) |
| v25.9.2 | 2023-12-18 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v25.9.2/) |
| v22.3.27 | 2023-12-18 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v22.3.27/) |
| v20.0.3 | 2022-10-10 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v20.0.3/) |
| v19.1.9 | 2023-08-07 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v19.1.9/) |
| v17.4.7 | 2023-03-09 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v17.4.7/) |
| v17.4.0 | 2022-05-27 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v17.4.0/) |
| v16.2.3 | 2022-05-27 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v16.2.3/) |
| v15.5.2 | 2022-05-20 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v15.5.2/) |
| v15.0.0 | 2022-05-20 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v15.0.0/) |
| v13.6.9 | 2022-05-20 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v13.6.9/) |
| v12.0.9 | 2022-03-10 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v12.0.9/) |
| v8.5.5 | 2022-03-10 | 标准版 | [下载](https://ftp.loongnix.cn/electron/LoongArch/v8.5.5/) |

<a id="lsx-优化版说明"></a>

### LSX 优化版说明

- 特性调整：修复2K3000部分显示异常问题
- 编译配置：当前版本默认开启lsx自动向量优化。
