# LoongArch上pi使用指南

Pi 是极简 AI 智能体框架，支持按需适配现有工作流，自带统一大模型接口、Agent 调度、终端 TUI 交互与代码智能体能力。可通过扩展、技能、提示词模板、主题自定义，打包后通过 npm 或 git 分发；默认配置精简，不内置子代理、计划模式等能力，可自行构建或安装扩展包补齐。

上游仓库：[https://github.com/earendil-works/pi](https://github.com/earendil-works/pi)

**版本说明:**

- **可用版本**：1.3.0
- **Node.js 版本要求**：> 22.19.0
- **支持 ABI**：仅 ABI2.0

## 全局安装与运行：
```
$ npm install -g --ignore-scripts @earendil-works/pi-coding-agent
$ pi
```