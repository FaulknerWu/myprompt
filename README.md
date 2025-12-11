# Claude Code 自定义提示词配置

一套 Claude + Codex 协作工作流的提示词配置。

## 前置依赖

安装 Codex Skills：[cexll/myclaude](https://github.com/cexll/myclaude)

## 核心功能

- Claude 负责：任务分析、架构规划、文档更新、简单代码修改
- Codex 负责：上下文收集、复杂代码修改、测试执行、代码审查
- MCP 工具规则：技术 API 优先查 context7，非技术问题用 exa

## 变体说明

| 变体 | 说明 | 适用场景 |
|------|------|----------|
| `default/` | 完整工作流，详细阶段定义 | 需要严格流程控制 |
| `acemcp/` | 集成 Augment MCP 语义搜索 | 大型代码库 |
| `lite/` | 精简版，仅保留核心约束 | 偏好模型自主判断 |

## lite 版本特点

- 用 4 个检查点替代 7 阶段工作流
- 删除 fallback/timeout/session 规则
- 删除详细的 challenge-protocol
- 精简任务模板，保留核心字段
- 行数减半，token 消耗更低
