# 使用 nvm 安装 Node.js 教程

> 适用架构：LoongArch（龙芯）ABI1.0 | ABI2.0

参考文档：
- Node.js 中文文档：[https://nodejs.cn/learn/introduction-to-nodejs](https://nodejs.cn/learn/introduction-to-nodejs)
- nvm 官方文档：[https://github.com/nvm-sh/nvm](https://github.com/nvm-sh/nvm)

## 一、安装 nvm
nvm 是 Node.js 版本管理器，可实现多版本 Node.js 的一键安装、切换、查询，适合开发环境多版本管理。

### 1.1 一键安装 nvm
任选以下一种命令执行官方安装脚本：
#### 方式 1：使用 curl 命令
```
$ curl -o- https://ftp.loongnix.cn/nodejs/npm-registry/LoongArch/abi-v1.0/nvm/v0.39.2/install.sh | bash
```
#### 方式 2：使用 wget 命令
```
$ wget -qO- https://ftp.loongnix.cn/nodejs/npm-registry/LoongArch/abi-v1.0/nvm/v0.39.2/install.sh | bash
```

> 脚本执行说明：
> 1. 自动下载nvm核心脚本（nvm-exec、bash_completion、nvm.sh）；
> 2. 脚本统一存放至~/.nvm目录；
> 3. 自动检测并向shell配置文件（`~/.bashrc`、`~/.bash_profile`、`~/.zshrc`、`~/.profile`）添加nvm环境变量。

#### 1.2 手动配置 nvm 环境变量（自动配置失败时）
如果执行完脚本后终端提示 `nvm: command not found`，执行下面命令:
```
$ export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # 加载nvm核心功能
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # 加载nvm命令补全功能
```

## 二、安装 Node.js
### 2.1 ABI1.0 环境安装
1. 查看 LoongArch ABI1.0 支持的全部 Node.js 版本:
```
$ nvm ls-remote node
       v10.24.1   (LTS: Dubnium)
       v10.24.2   (Latest LTS: Dubnium)
       v12.19.1   (LTS: Erbium)
       v12.22.12   (Latest LTS: Erbium)
       v14.16.1   (LTS: Fermium)
       v14.21.3   (Latest LTS: Fermium)
       v16.3.0
       v16.5.0
       v16.17.1   (LTS: Gallium)
       v16.20.1   (LTS: Gallium)
       v16.20.2   (Latest LTS: Gallium)
       v18.13.0   (LTS: Hydrogen)
       v18.18.1   (LTS: Hydrogen)
       v18.19.1   (LTS: Hydrogen)
       v18.20.2   (LTS: Hydrogen)
       v18.20.3   (LTS: Hydrogen)
       v18.20.8   (Latest LTS: Hydrogen)
       v20.8.0
       v20.11.1   (LTS: Iron)
       v20.13.0   (LTS: Iron)
       v20.13.1   (LTS: Iron)
       v20.19.2   (LTS: Iron)
       v20.19.4   (Latest LTS: Iron)
       v21.7.3
       v22.1.0
       v22.16.0   (Latest LTS: Jod)
```
2. 安装指定版本
```
$ nvm install 22.16.0
```
3. 验证安装结果
```
$ node -v
v22.16.0
```
### 2.2 ABI2.0 环境安装
ABI2.0 可安装版本清单参考：[ABI2.0 支持的 Node.js 版本清单](../stats/abi2.0_nodejs_supported_versions.md)

1. 先配置二进制包镜像源
```
$ export NVM_NODEJS_ORG_MIRROR="https://unofficial-builds.nodejs.org/download/release/"
```
2. 安装目标版本
```
$ nvm install v24.8.0
```
3. 校验版本
```
$ node -v
v24.8.0
```

## 三、运行 Hello World 程序
### 3.1 交互式命令行模式
直接输入 `node` 进入 REPL 交互环境，即时执行代码：
```
$ node
> console.log('Hello World!');
Hello World!
>
```
### 3.2 脚本文件模式
1. 创建代码文件
```
$ vim hello-world.js
```
2. 写入代码内容
```
console.log('Hello World!');
```
3. 执行脚本
```
$ node hello-world.js
Hello World!
```

