# Claude Code 自定义提示词配置

一套 Claude + Codex 协作工作流的提示词配置。

## 前置依赖

安装 Codex Skills：[cexll/myclaude](https://github.com/cexll/myclaude)

## 核心功能

- Claude 负责：任务分析、架构规划、文档更新、简单代码修改
- Codex 负责：上下文收集、复杂代码修改、测试执行、代码审查
- MCP 工具规则：技术 API 优先查 context7，仓库结构优先查 deepwiki
