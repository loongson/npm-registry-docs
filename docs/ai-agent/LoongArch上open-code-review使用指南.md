# LoongArch上open-code-review使用指南

Open-Code-Review 是阿里开源的混合架构代码评审工具，安全、高速高效，已在阿里大规模业务场景实战验证。采用确定性流水线 + LLM Agent 架构，可生成精确到代码行的评审意见；内置多语言检测规则，覆盖空指针异常、线程安全、XSS、SQL 注入等问题，兼容 OpenAI、Anthropic 接口。


上游仓库：[https://github.com/alibaba/open-code-review](https://github.com/alibaba/open-code-review)

**版本说明:**

- **可用版本**：v1.12.11
- **支持 ABI**：仅 ABI2.0