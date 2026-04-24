---
title: Observability / Cost / Trace
tags: [agent-learning, topic, observability]
status: active
---

# Observability / Cost / Trace

## 这页回答什么

如何让 Agent 系统变得可诊断、可解释、可控成本。

## 对应周次

- [[Agent-Learning/Week-02_2026-04-27|Week 02]]:Token Logger 与 audit_log 起点
- [[Agent-Learning/Week-03_2026-05-04|Week 03]]:structlog 统一 session 事件
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]:CostTracker、Trace/Span、CLI 展示

## 关注点

- 每次 LLM 调用有没有 token 与时延数据
- 每次工具调用有没有审计记录
- 一个 session 能否串起所有事件
- 是否能快速定位 token 超支 / 死循环 / 质量回退来源

## 验证标准

- 单 session 可回放
- token 成本可聚合
- trace 能定位问题阶段和责任组件
