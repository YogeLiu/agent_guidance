---
title: Planning
tags: [agent-learning, topic, planning]
status: active
---

# Planning

## 这页回答什么

任务什么时候需要显式计划,计划如何执行,以及计划失败后如何修正。

## 核心组成

- Planner
- Executor
- Plan Schema
- Replanner
- Token Budget
- 状态持久化

## 对应周次

- [[Agent-Learning/Week-04_2026-05-11|Week 04]]:Planning System 全量引入
- [[Agent-Learning/Week-05_2026-05-18|Week 05]]:Coordinator 四阶段调度继承 Planning 思想
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]:Planning 失败时降级到 single agent

## 核心判断

- 任务是否可预先分解?
- 显式计划是否带来更高质量或更低成本?
- Replan 是必要修复,还是设计不稳导致的补丁?

## 验证标准

- 复杂任务能先出计划再执行
- 执行过程状态可见
- 预算受控
- Replan 不会死循环
