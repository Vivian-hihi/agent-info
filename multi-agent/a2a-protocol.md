# Google Agent2Agent (A2A) 协议

> 发布时间：2025 年 4 月 9 日  
> 官方博客：https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/  
> GitHub：https://github.com/google/A2A

## 是什么

A2A（Agent2Agent）是 Google 发布的一个开放协议，目标是让**不同厂商、不同框架构建的 AI Agent 之间能够互相通信、协作**。

超过 50 家技术合作伙伴参与，包括 Atlassian、Salesforce、SAP、ServiceNow、LangChain、Cohere 等，以及 Accenture、Deloitte、McKinsey 等服务商。

## 和 MCP 的关系

| 协议 | 作用 |
|------|------|
| **MCP**（Anthropic） | Agent ↔ 工具/数据源（给 Agent 提供工具和上下文） |
| **A2A**（Google） | Agent ↔ Agent（让 Agent 之间互相协作） |

两者互补，不竞争。A2A 官方明确说"A2A complements MCP"。

## 五大设计原则

1. **拥抱 Agent 能力** — 支持真正的多 Agent 场景，Agent 不被降级为"工具"
2. **基于现有标准** — 构建在 HTTP、SSE、JSON-RPC 之上，易于集成
3. **默认安全** — 支持企业级认证授权，与 OpenAPI 认证方案对齐
4. **支持长时任务** — 从秒级任务到需要数小时甚至数天的深度研究都支持
5. **模态无关** — 不只是文本，支持音频、视频等多模态流式传输

## 核心机制

### Agent Card
每个 Agent 用 JSON 格式发布自己的能力描述（"名片"），客户端 Agent 据此找到最合适的 Agent 来完成任务。

### 角色划分
- **Client Agent** — 提出任务，协调调度
- **Remote Agent** — 接收任务，执行操作，返回结果（Artifact）

### 任务生命周期
```
任务创建 → 执行中（实时状态更新）→ 完成/失败
                ↕
           人类介入（可选）
```

### 消息结构
每条消息包含多个 **Part**（内容块），每个 Part 有指定的 content-type，支持客户端和远程 Agent 之间协商格式（包括 iframe、视频、Web 表单等 UI 能力）。

## 实际应用示例

**招聘场景：**
1. 招聘经理对主 Agent 说："帮我找符合这个 JD 的候选人"
2. 主 Agent 通过 A2A 与候选人搜索 Agent、背景核查 Agent、日程协调 Agent 分别协作
3. 汇总结果返回给招聘经理

## 对 OpenClaw 的意义

- OpenClaw 目前的多 Agent 是通过 `sessions_spawn` + `subagents` 实现的（内部协议）
- A2A 代表了跨平台、跨厂商多 Agent 协作的未来方向
- 如果 OpenClaw 未来支持 A2A，就能与 LangChain、Salesforce 等生态的 Agent 直接对话

## 参考链接

- [官方公告](https://developers.googleblog.com/en/a2a-a-new-era-of-agent-interoperability/)
- [GitHub 规范草案](https://github.com/google/A2A)
- [A2A vs MCP 对比讨论](https://x.com/search?q=A2A%20MCP%20protocol)
