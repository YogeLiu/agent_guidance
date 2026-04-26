---
title: Memory
tags: [agent-learning, topic, memory]
status: active
---

# Memory

## 这页回答什么

记忆系统到底要解决什么问题,哪些记忆类型真的值得存在。

## 核心原则

- Memory-as-Index
- Index / Payload 分离
- 跨会话持久化
- 必要性必须用真实数据证明

## 对应周次

- [[Agent-Learning/Week-03_2026-05-04|Week 03]]:四类记忆、写入决策、去重、持久化、使用率报告
- [[Agent-Learning/Week-05_2026-05-18|Week 05]]:Chaos 中验证 memory 异常边界
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]:Memory 失败时的降级策略

## 真正要回答的不是“怎么存”

而是:

- 哪些内容值得长期保存?
- 记忆是否真的减少重复搜索与 token 消耗?
- 哪些类型根本没有被用到,应该砍掉?

## 验证标准

- 偏好跨会话保留
- 失效引用可检测
- Index 注入 token 受控
- 4 类记忆是否保留由真实使用数据决定
