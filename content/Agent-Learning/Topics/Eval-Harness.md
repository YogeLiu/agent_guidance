---
title: Eval Harness / Baseline
tags: [agent-learning, topic, eval]
status: active
---

# Eval Harness / Baseline

## 这页回答什么

怎样判断 Agent 是真正变好,还是只是换了一种感觉上更复杂的写法。

## 核心思想

- Eval-Driven
- Baseline-Tracked
- Mock-First
- LLM-as-Judge + golden answer

## 对应周次

- [[Agent-Learning/Week-02_2026-04-27|Week 02]]:工业化 Eval Harness 起点 + W2 baseline
- [[Agent-Learning/Week-03_2026-05-04|Week 03]]:加入 Memory 用例并与 W2 比较
- [[Agent-Learning/Week-04_2026-05-11|Week 04]]:支持 ReAct vs Plan-Act A/B
- [[Agent-Learning/Week-05_2026-05-18|Week 05]]:支持 Multi-Agent / Routing 决策
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]:三个 Agent 全集回归

## 学习时真正要看什么

- case 设计是否覆盖关键失败模式
- judge criteria 是否具体
- baseline 是否能支持架构决策
- mock 与 real 的边界是否清楚

## 验证标准

- 开发循环能用 mock 快速跑
- 周末能跑真 LLM 验证
- 每周有可追溯 baseline JSON
- 任何退化都能被定位,而不是靠印象
