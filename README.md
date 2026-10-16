# LoongArch NPM Registry Docs
LoongArch npm私有源配套文档仓库，包含AI-Agent工具包教程、Electron打包工具使用文档，以及ABI1.0/ABI2.0软件包统计信息。

## 文档导航


- [LoongArch npm 仓库地址配置](#1-loongarch-npm-仓库地址配置)
- [AI Agent 工具包使用教程](./docs/AI‑Agent工具包使用教程.md)
- [Electron‑Builder 使用教程](./docs/Electron‑Builder使用教程.md)
- [Electron‑Packager 使用教程](./docs/Electron‑Packager使用教程.md)
- [ABI1.0 已移植包统计列表](./stats/abi1.0_packages_stats.md)
- [ABI2.0 已移植包统计列表](./stats/abi2.0_packages_stats.md)


## 1. LoongArch npm 仓库地址配置

LoongArch分为 **ABI1.0 / ABI2.0** 两套ABI，两套仓库互相不兼容，对应独立的npm镜像源，请务必确认系统ABI版本后配置对应npm源。

### 1.1 查看系统 ABI 版本
执行以下终端命令，快速识别当前系统的 LoongArch ABI 版本：
```bash
$ LC_ALL=C readelf -h /bin/bash  | grep Flags: | awk -F' ' '{ print $2 }'
```
结果对应说明：
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

## License
本仓库全部文档内容遵循 **CC‑BY‑4.0（署名4.0国际）** 许可协议。
详见 [LICENSE](./LICENSE)



