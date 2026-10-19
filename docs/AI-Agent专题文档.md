# AI Agent专题文档

> 部分工具包**仅提供 ABI2.0 平台移植版本**，无法在ABI1.0环境安装运行。安装前请确认LoongArch系统的ABI版本，留意各软件包标注的ABI适配范围。

## 1. LoongArch npm 仓库地址配置

LoongArch分为 **ABI1.0 / ABI2.0** 两套ABI，两套仓库互相不兼容，对应独立的npm镜像源，请务必确认系统ABI版本后配置对应npm源。
### 1.1 查看系统 ABI 版本
执行以下终端命令，快速识别当前系统的 LoongArch ABI 版本：
```bash
$ LC_ALL=C readelf -h /bin/bash  | grep Flags: | awk -F' ' '{ print $2 }'
```
输出结果说明：
- 输出 0x3, → 当前系统为 ABI 1.0
- 输出 0x43, → 当前系统为 ABI 2.0

### 1.2 ABI1.0 环境配置源
```bash
$ npm set registry https://registry.loongnix.cn:4873
```
### 1.3 ABI2.0 环境配置源
```bash
$ npm set registry https://registry.loongnix.cn:5873
```

### 1.4 验证源配置是否生效
配置完成后，通过以下命令查看当前生效的 npm 源，确认配置无误：
```bash
$ npm config get registry
```

## 2. 软件包使用说明

### 2.1 软件包：deepseek-harness

- **支持 ABI**：ABI1.0 (0.1.1‑rc.2)｜ABI2.0 (0.1.1‑rc.2 ~ 最新)
- **Node 版本要求**：>=v22.16.0

**ABI1.0 安装启动:**
> ABI1.0 仅可使用 `0.1.1‑rc.2` 版本
```bash
$ npm install @deepseek-ai/dsh@0.1.1‑rc.2
```
启动 web 服务：
```bash
$ node --expose-internals ./node_modules/@deepseek-ai/dsh/lib/bin.js web
```
**ABI2.0 安装启动:**

使用npx进行安装使用
```
$ npx @deepseek-ai/dsh web
```

### 2.2 软件包：opencode

- **支持 ABI**：仅 ABI2.0
- **可用版本**：`1.17.11`、`1.19.0`

**全局安装并运行：**
```bash
$ npm install -g opencode-ai@1.17.11
$ opencode
```

### 2.3 软件包：openclaw

- **支持 ABI**：仅 ABI2.0
- **可用版本**：`2026.5.7` ~ 最新版本


**全局安装并运行：**
```bash
$ npm install -g openclaw@2026.5.7
$ openclaw onboard --install-daemon
```

### 2.4 软件包：codex

- **支持 ABI**：仅 ABI2.0
- **可用版本**：`0.148.0`、`0.154.0`

**全局安装并运行：**
```bash
$ npm install -g codex@0.154.0
$ codex
```
