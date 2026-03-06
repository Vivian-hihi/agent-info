# OpenClaw 笔记

OpenClaw 是一个个人 AI 助手框架，支持多平台接入（Telegram、Discord、Signal 等）。

## 目录

- [基础配置](./setup.md)
- [Skills 使用](./skills.md)
- [常见问题](./faq.md)

## 核心概念

- **主会话 (Main Session)** — 与你直接对话的助手实例
- **子 Agent (Sub-agent)** — 由主会话派生的隔离任务执行单元
- **Skills** — 扩展能力包，如 GitHub、飞书、天气等
- **Heartbeat** — 定时心跳，让 Agent 主动检查邮件/日历等
- **Cron** — 精确定时任务调度

## 常用命令

```bash
openclaw status          # 查看运行状态
openclaw gateway start   # 启动 Gateway 服务
openclaw gateway status  # 查看 Gateway 状态
```
