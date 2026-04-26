---
title: Agent Loop
tags: [agent-learning, topic, agent-loop]
status: active
---

# Agent Loop

## 这页回答什么

从零实现一个可运行的 Agent 主循环:用户输入,LLM 决策,工具执行,结果回注,直到得到最终回答。

## 为什么重要

这是所有后续能力的承载层。没有稳定 loop,后面的 Tool / Reflection / Planning 都会漂浮。

## 核心问题

- 最小闭环是什么?
- tool call 如何进入循环?
- 工具错误如何反馈给 LLM 而不是直接崩掉?
- 流式输出和 retry 放在哪一层最合适?

## 本主题范围

- 最小消息循环
- tool call 检测与再调用
- 流式输出
- retry 与错误恢复

## 对应周次

- [[Agent-Learning/Week-01_2026-04-20|Week 01]]:最小 loop + 流式输出 + tool call 闭环
- [[Agent-Learning/Week-02_2026-04-27|Week 02]]:迁移到 `LLMClient` 抽象
- [[Agent-Learning/Week-04_2026-05-11|Week 04]]:与 Planning / LangGraph 的归宿决策

## 验证标准

- 工具能被调用并把结果重新注入 LLM
- 工具失败时 Agent 不崩,而是继续修正
- 用户能看到执行进度,不是黑盒等待

## 常见误区

- 一开始就引完整框架,导致看不见 loop 的本质
- 把 retry、reflect、replan 混成一件事
- tool error 直接抛异常给终端,不给 LLM 修正机会

## 回看时重点

先看 W1 的最小闭环,再看 W4 为什么要决定 `agent_loop.py` 的去留。
