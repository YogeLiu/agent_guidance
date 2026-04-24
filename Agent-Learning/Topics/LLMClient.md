---
title: LLMClient / Provider 抽象
tags: [agent-learning, topic, llmclient]
status: active
---

# LLMClient / Provider 抽象

## 这页回答什么

为什么业务代码不能直接调用 SDK,以及一个最薄但足够用的 `LLMClient` 应该承担哪些职责。

## 目标

- 隔离 provider 差异
- 聚合 token / latency 统计
- 支持 mock / replay
- 让 eval 与业务代码共用同一调用边界

## 对应周次

- [[Agent-Learning/Week-02_2026-04-27|Week 02]]:首次抽象 + Token Logger + Mock 模式
- [[Agent-Learning/Week-04_2026-05-11|Week 04]]:接 Planning 与范式对比
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]:CostTracker 与 Trace 复用既有埋点

## 验证标准

- 切 provider 只改一层
- eval 可以替换成 `MockLLMClient`
- token / duration 统计天然落盘,不是事后补埋点

## 风险点

- 抽象过厚,变成半个框架
- 业务层偷偷绕过 `LLMClient` 直接打 SDK
