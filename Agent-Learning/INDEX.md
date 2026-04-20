---
title: Agent Learning — 学习路径总览
tags:
  - agent-learning
  - index
aliases:
  - Agent学习总览
status: active
created: 2026-04-20
---

# Agent Learning — 学习路径总览

## 贯穿项目：ResearchAgent

一个真实可用的个人研究助手，分阶段演进，每周新增一个核心能力。

---

## 学习路径

```mermaid
graph LR
    W1["Week 01\n工具链 + Tool System 启动"] --> W2["Week 02\nTool System 完成\nMVP 交付"]
    W2 --> W3["Week 03\nMemory System"]
    W3 --> W4["Week 04\nPlanning System"]
    W4 --> W5["Week 05\nMulti-Agent 基础"]
    W5 --> W6["Week 06\n系统集成\n最终交付"]

    style W1 fill:#ff6b6b,color:#fff
    style W2 fill:#ffa502,color:#fff
    style W3 fill:#2ed573,color:#fff
    style W4 fill:#1e90ff,color:#fff
    style W5 fill:#a29bfe,color:#fff
    style W6 fill:#fd79a8,color:#fff
```

---

## 周计划索引

| 周次 | 日期 | 阶段 | 核心能力 | 交付物 |
|---|---|---|---|---|
| [[Agent-Learning/Week-01_2026-04-20\|Week 01]] | 04-20 ~ 04-26 | 阶段0+1 | Agent Loop · Tool System 启动 | 可运行的 Agent Loop + 工具注册表 |
| [[Agent-Learning/Week-02_2026-04-27\|Week 02]] | 04-27 ~ 05-03 | 阶段1 | Tool System 完整 · MVP | ResearchAgent MVP |
| [[Agent-Learning/Week-03_2026-05-04\|Week 03]] | 05-04 ~ 05-10 | 阶段2 | Memory System | 四类记忆 + AutoDream |
| [[Agent-Learning/Week-04_2026-05-11\|Week 04]] | 05-11 ~ 05-17 | 阶段3 | Planning System | Planner + Executor + Replanner |
| [[Agent-Learning/Week-05_2026-05-18\|Week 05]] | 05-18 ~ 05-24 | 阶段4上 | Multi-Agent 基础 | Coordinator + 3 类 Worker |
| [[Agent-Learning/Week-06_2026-05-25\|Week 06]] | 05-25 ~ 05-31 | 阶段4下 | 系统集成 + Observability | 完整 ResearchAgent |

---

## 系统演进

```
Week 02 MVP
  单 Agent + 6 工具 + CLI

Week 03 加 Memory
  + 四类记忆（user/feedback/project/reference）
  + 跨会话记忆持久化
  + AutoDream 自动记忆提取

Week 04 加 Planning
  + Planner-Executor 分离
  + 动态 Replanning
  + Token 预算控制
  + 任务中断恢复

Week 06 最终系统
  + Coordinator/Worker 多 Agent
  + 并发控制
  + Cost Tracking
  + Trace/Span Observability
```

---

## 技术栈

| 层 | 技术 | 引入时机 |
|---|---|---|
| LLM 调用 | Anthropic SDK（直接） | Week 01 |
| Schema 验证 | Pydantic v2 | Week 01 |
| 状态机 | LangGraph | Week 04 |
| 搜索 | Tavily API | Week 01 |
| 存储 | 文件系统 + SQLite | Week 01/03 |
| Observability | 自研 Tracer + LangSmith（可选）| Week 06 |

> [!warning] 禁止早期引入
> LangChain / AutoGen / CrewAI 整个学习期间不使用。

---

## 核心设计原则

> [!quote] Permission-First
> 每个工具默认拒绝，显式授权。`needs_permission()` 返回 `allow | deny | ask_user`。

> [!quote] Memory-as-Index
> 记忆是检索系统，不是全量上下文。Index 始终加载（< 1000 tokens），Payload 按需读取。

> [!quote] Coordinator-Worker Pattern
> Multi-Agent 不是对等的。Coordinator 负责合成理解（不可委托），Worker 接收自包含 Prompt。

> [!quote] Cost-as-First-Class-Concern
> Token 预算和成本追踪是核心基础设施，不是事后添加。

---

## 参考资料

- [[agent_learn_guidance|原始路线图评估]]
- [Anthropic SDK 文档](https://docs.anthropic.com)
- [LangGraph 文档](https://langchain-ai.github.io/langgraph/)
- [Tavily API](https://tavily.com)
