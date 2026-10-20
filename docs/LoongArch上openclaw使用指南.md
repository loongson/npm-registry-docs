# LoongArch上openclaw使用指南

openclaw 是一款开源本地 AI 智能体框架。与传统的对话框 AI 不同，OpenClaw 可以接管你的微信、Telegram、日程表甚至 GitHub，在后台 24/7 自动执行任务，能够通过自然语言指令在你的电脑上执行真实操作，如整理文件、编写代码、管理邮件、自动浏览网页等 。

**openclaw部署环境要求:**

* **操作系统**：主流 Linux 发行版
* **内存**：至少 1 GB RAM
* **网络**：开放`18789`端口
* **Node.js**：OpenClaw 推荐使用 Node.js 24+

## 一、Loongnix25上部署openclaw步骤

### 1.1 使用 nvm 安装 Node.js

1. 安装wget命令

```
$ apt update 
$ apt install wget
```

2. 一键安装 nvm 命令

任选以下一种命令执行官方安装脚本：

方式 A：使用 curl 命令
```
$ curl -o- https://ftp.loongnix.cn/nodejs/npm-registry/LoongArch/abi-v1.0/nvm/v0.39.2/install.sh | bash
```
方式 B：使用 wget 命令
```
$ wget -qO- https://ftp.loongnix.cn/nodejs/npm-registry/LoongArch/abi-v1.0/nvm/v0.39.2/install.sh | bash
```

3. 配置镜像并安装 Node.js

```
$ export NVM_NODEJS_ORG_MIRROR="https://unofficial-builds.nodejs.org/download/release/"
$ nvm install v24.8.0
```

4. 验证安装，输出版本号即成功
```
$ node -v
v24.8.0
```

### 1.2 使用 npm 安装 openclaw 软件

1. 配置 npm 仓库为 ABI2.0 的仓库

```
$ npm set registry https://registry.loongnix.cn:5873
```

2. 使用 npm 全局安装 openclawopenclaw

```
$ npm install -g openclaw
```

![](../images/flQjAe-2UMJ0EsUwwqAmtCov1NKIuGbShu2pTXX3cVc=.png)

3. 验证安装

执行以下命令，正常输出版本及配置项，说明安装成功。

![](../images/pqVxo5inJKyA-u9XBwD0l0AUYlMttRKIvzDz-PL1n1I=.png)

### 1.3.openclaw 的部署和使用

执行初始化命令，进入交互式部署流程：

```
$ openclaw onboard --install-daemon
```
按下面顺序完成配置：

1. 输出如下所示，选择 yes 进行部署配置

![](../images/zg9YShhPZ8ogM9KD6S6sSJV5zI_uodnXpsFxgBFV5Qk=.png)

2. 选择yes后到 Onboarding mode 选择模式为快速开始 QuickStart

![](../images/LaA8Ubqpkk1rjncMwx2KdBLbYZcNLIC1QgYFGyIhoeY=.png)

3. 选择快速开始后，出现的界面上面小方框是 openclaw 网关的基础信息，下面列表是挑选AI大模型的供应商，以常用的大模型 MiniMax 为例，选项移到 MiniMax ,输入回车

![](../images/NygGB2nC9Lz8Z41PvK9D_998LbSCynSASw8JtJQfH5I=.png)

4. 回车后，是选择大模型的验证方式界面，选择带 CN 后缀的 API Key 方式，带 CN 后缀是国内使用的大模型网址，Global 后缀是国外使用的大模型网址

![](../images/9sKkyM7YuhwcCVOYZ_UWJXGYrrAZYJdzipDKtqBGnM4=.png)

5. 选择 API Key 的验证方式后，是选择提供 API key 的方式，第一个选项是立即粘贴提供，第二个方式是外部提供，通过环境变量或其他配置项提供，这里选择第一个

![](../images/76WNqGveuefTSvmTdoNSRAmT3XQEIcqRlpxLu2oJS7s=.png)

6. 选择后就是粘贴大模型提供的 API key 到输入光标位置，输入后回车

![](../images/boI3G4SoDGLF2NlaXzB7lql8lhVjhkE9EtAX7VJMy7k=.png)

7. 回车后是选择大模型的版本，这里选择的是 MiniMax-M2.5 的大模型版本，输入回车

![](../images/5b-dG-NFiKOP9c22X3IN3UTzd_i12QpW8jKoGseFSXo=.png)

8. 回车后是选择 channel, 这是对接聊天工具的通道，这里先跳过，后续有需要可以在webui界面自行配置

![](../images/P80n2kAnjiCnmAdueBc7LKeDkl_leoi3MWl_ubsqw_o=.png)

9. 接下来是搜索提供商，当 AI 需要进行网络搜索以获取实时信息时所使用的搜索引擎服务。它决定了 OpenClaw 在执行 web\_search 工具时调用哪个后端搜索服务，这里可以选择跳过

![](../images/tGRaNnNFIE0PGkMOcpZMOYuIq5j_SuVj4gMcOL6BNtg=.png)

10. 跳过后是配置 skills 界面，这个可以选择 No 跳过，后续有需要可以再 openclaw 的 webui 界面配置

![](../images/o6Yu8rdwa_iKerqDCtp4B4Uurarms1tvJ0BhfU8IkyM=.png)

11. 跳过后是 hooks 的配置，这个配置是在发出代理命令时可以自动执行的操作，可以根据需求进行配置，也可以后续在 webui 界面进行配置，这里先跳过，通过空格键选择，回车执行

![](../images/QYZ9__XksabPt-VxfFA-9V5giF82v8wgQ5Iq_Ain38g=.png)

12. 跳过 hooks 配置后 openclaw 会自动安装 openclaw 网关服务，安装完毕后会显示服务安装路径和会话缓存路径，在 control ui 框有 openclaw 的 webui 访问网址链接，可通过网页访问 webui 界面对 openclaw 进行配置和使用

![](../images/OujY7ismK0GZ2KOW-GmTCrqh40CIklCJNJtvLsJEln8=.png)

13. 安装完 openclaw 的网关服务后，可以选择 TUI 和 Web UI 来与 openclaw 进行交流

![](../images/lRK5iVBiOvm-YAX-mVPBpFYsaGcBUPM4z5HYG-fFW6Q=.png)

#### 交互使用方式
网关部署完成，提供两种交互界面：TUI 终端界面、Web UI 网页界面。

1. TUI 终端界面

选择 TUI 的对话界面，光标输入框为交流对话框

![](../images/oDg22DQc-oOV_MxZm9I0d5oKUcdbfR2lkTQ5kaQu_To=.png)

2. Web UI 网页界面

选择 Web UI 的画面，则在浏览器上打开 openclaw 的配置和聊天界面

![](../images/F5xcVme3VyyvAN5LB05UI5c0bT7DEN0A7ZLEZPwDuhs=.png)

> openclaw 的 Web UI 的功能界面在左上角的功能栏，可以根据自己需求进行配置
>![](../images/ak_Jga4z3m81zI2fzbCI2upNtanLKZ0YdQVBd6BeZ2E=.png)
