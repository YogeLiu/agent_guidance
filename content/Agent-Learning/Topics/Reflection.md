---
title: Reflection
tags: [agent-learning, topic, reflection]
status: active
---

# Reflection

## 这页回答什么

如何区分 retry、in-task critic、cross-task replan,避免把三件不同的事混成一个“自我修正”。

## 三层边界

- `retry`:网络/API/瞬时失败
- `in-task critic`:当前任务结果不满足要求,在 task 内修正
- `cross-task replan`:task 内修正失败,上抛重新规划

## 对应周次

- [[Agent-Learning/Week-02_2026-04-27|Week 02]]:Reflection 雏形,最终回答前做一次 critic
- [[Agent-Learning/Week-04_2026-05-11|Week 04]]:完整闭环,明确 in-task 与 replan 分工
- [[Agent-Learning/Week-05_2026-05-18|Week 05]]:Chaos 中验证结构化恢复能力

## 常见错误

- 把所有失败都送去 Replan
- critic 没有明确成功标准,导致来回改写
- 反思层没有上限,导致死循环或 token 爆炸

## 验证标准

- 不满足 task description 时优先 task 内修正
- 只有 task 内确实失败时才 Replan
- 反思机制有次数上限和可解释日志
