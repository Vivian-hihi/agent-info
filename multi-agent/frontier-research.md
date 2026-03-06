# 前沿 Agent 研究动态（2025）

持续更新的 AI Agent 领域重要研究与进展。

---

## 🔥 2025 年值得关注的方向

### 1. Agent 协议标准化
- **A2A（Google）** — Agent 间互通协议 → [详见](./a2a-protocol.md)
- **MCP（Anthropic）** — Agent 与工具/数据源连接标准，已成为事实标准，大量框架支持
- 趋势：整个行业在推动 Agent 生态像 HTTP 一样标准化

### 2. LLM as OS（操作系统化）
Andrej Karpathy 等人提出的概念：LLM 不再只是模型，而是类似操作系统的核心——
- LLM = CPU（推理核心）
- Context Window = RAM（工作内存）
- 外部存储 = 硬盘
- Tools/Plugins = 外设驱动

代表产品：OpenAI Operator、Devin、Claude Computer Use

### 3. 多 Agent 框架百花齐放

| 框架 | 特点 |
|------|------|
| **LangGraph** | 基于图的 Agent 编排，支持循环和状态管理 |
| **AutoGen（微软）** | 多 Agent 对话框架，Agent 之间可以相互对话完成任务 |
| **CrewAI** | 角色扮演式多 Agent，每个 Agent 有明确职责 |
| **OpenAI Swarm** | 轻量级多 Agent 交接（handoff）框架 |
| **Dify** | 低代码 Agent 构建平台，国内广泛使用 |

### 4. Memory 机制研究
Agent 的记忆系统是当前热点：
- **短期记忆** — Context window（有限）
- **长期记忆** — 向量数据库（RAG）
- **情景记忆** — 会话历史压缩与检索
- **程序性记忆** — 从过去任务中学习新的操作流程

代表研究：MemGPT、Zep、mem0

### 5. Computer Use / GUI Agent
让 Agent 直接操控电脑界面（不依赖 API）：
- **Claude Computer Use**（Anthropic）— 截图 + 鼠标键盘操作
- **OpenAI Operator** — 浏览器自动化
- **UI-TARS（字节跳动）** — 端到端 GUI 操作模型，开源，国内领先
- **OmniParser（微软）** — 通用 UI 解析

### 6. Agent 评估与 Benchmark
- **SWE-bench** — 真实 GitHub issue 修复能力测试（代码 Agent 标准 benchmark）
- **WebArena / WorkArena** — Web 操作能力评估
- **GAIA** — 通用 AI 助手能力评估
- **AgentBench** — 综合多场景 Agent 评估

---

## 📄 近期重要论文

### Agent 规划与推理
- **ReAct**（2023）— Reasoning + Acting 交替进行，成为 Agent 标准范式
- **Reflexion**（2023）— Agent 通过自我反思改进输出
- **Tree of Thoughts**（2023）— 树状搜索推理，提升复杂任务表现

### 多 Agent 协作
- **AgentVerse** — 模拟多 Agent 协作解决复杂问题
- **MetaGPT**（2023）— 用软件公司角色分工模拟多 Agent 协作

### 长上下文与记忆
- **MemGPT**（2023）— 分层记忆管理，突破上下文限制

---

## 🧭 趋势判断

1. **协议标准化** 是接下来 1-2 年的主战场，A2A + MCP 会成为基础设施
2. **GUI Agent** 将极大扩展 Agent 能处理的任务边界（不依赖 API）
3. **Agent 可靠性** 是商业落地最大瓶颈，Eval + 监控工具需求大增
4. **个人 Agent**（如 OpenClaw）和**企业 Agent**（如 ServiceNow + A2A）会形成两条赛道

---

*最后更新：2026-03-06*
