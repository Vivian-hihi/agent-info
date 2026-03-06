# 多 Agent 协同

探索多个 AI Agent 协作完成复杂任务的模式与实践。

## 常见协同模式

### 1. 主从模式
主 Agent 负责规划和调度，子 Agent 负责执行具体任务。

```
主 Agent
├── 子 Agent A（代码任务）
├── 子 Agent B（搜索任务）
└── 子 Agent C（写作任务）
```

### 2. 流水线模式
多个 Agent 串行处理，前一个的输出作为下一个的输入。

### 3. 并行模式
多个 Agent 同时处理不同子任务，最后汇总结果。

## OpenClaw 中的多 Agent

- `sessions_spawn` — 派生新的子 Agent 会话
- `subagents` — 管理运行中的子 Agent（list/steer/kill）
- `sessions_send` — 向其他会话发送消息
- ACP harness — 在 Discord thread 中运行 Codex/Claude Code 等

## 实践案例

见 [daily/](../daily/) 目录中的每日记录。
