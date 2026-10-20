# 使用nvm安装Node.js教程

## 一、通过nvm安装Node.js
nvm是Node.js版本管理器，可便捷实现多版本Node.js的安装、切换、查看等操作。以下以安装Node.js v14.16.1为例说明步骤。

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
> 3. 自动检测并向shell配置文件（~/.bashrc、~/.bash_profile、~/.zshrc、~/.profile）添加nvm环境变量。

#### 1.2 手动配置 nvm 环境变量（自动配置失败时）
若终端无法识别nvm命令，执行以下命令临时配置（添加至上述shell配置文件可永久生效）：
```
$ export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # 加载nvm核心功能
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # 加载nvm命令补全功能
```

### 1.3 查看LoongArch架构支持的Node.js版本

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
> 注：实际显示版本以终端输出为准

### 1.4 安装指定版本Node.js

 ```
$ nvm install 14.16.1
```

### 1.5 验证安装版本

```
$ node -v
V14.16.1
```

## 二、运行Hello World程序
### 2.1 交互模式
终端输入node进入交互环境，执行代码并实时查看结果：

```
$ node
> console.log('Hello World!');
Hello World!
>
```

### 2.2 脚本模式
以下是Node.js程序:

```
# 创建脚本文件：
$ vim hello-world.js

# 写入代码：
console.log('Hello World!');

# 执行脚本：
$ node hello-world.js
Hello World!
```

## See Also：
npm官方教程文档:  https://www.npmjs.com/package/doc

nodejs中文文档:  https://nodejs.cn/learn/introduction-to-nodejs

nvm官方文档：  https://github.com/nvm-sh/nvm

---
