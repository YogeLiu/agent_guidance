---
title: Multi-Agent vs Routing
tags: [agent-learning, topic, multi-agent]
status: active
---

# Multi-Agent vs Routing

## 这页回答什么

什么时候真的需要 Multi-Agent,什么时候模型路由已经足够。

## 默认立场

默认应假设**不需要 Multi-Agent**。只有 single agent 明确不够时才升级。

## 对应周次

- [[Agent-Learning/Week-05_2026-05-18|Week 05]]:必要性证伪、决策门、Multi-Agent 或 Routing 分叉
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]:横向迁移后复盘这个判断是否仍然成立

## 决策指标

- judge score 是否显著提升
- latency 是否下降
- token 是否持平或更优
- 系统复杂度是否值得新增收益

## 学习重点

- Coordinator 的工作不能被误委托
- Worker Prompt 必须自包含
- 并行是收益来源,不是“多个 agent”本身
- 如果收益不明显,诚实回到 routing 或 single agent
