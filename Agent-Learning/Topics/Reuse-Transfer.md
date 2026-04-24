---
title: Reuse / Transfer
tags: [agent-learning, topic, reuse]
status: active
---

# Reuse / Transfer

## 这页回答什么

怎样证明你做出来的不是一个场景绑定 demo,而是一套真的可迁移基础设施。

## 三个验证层次

- 主项目:ResearchAgent
- 第二项目:CodeReviewAgent
- 第三项目:DataAnalysisAgent

## 对应周次

- [[Agent-Learning/INDEX|总览]]:三角度落地原则
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]:第二项目与第三项目正式验证

## 真正的判断标准

- 新项目新增代码有多少?
- 有没有改动禁区 `core/ planning/ agents/ evals/ observability/`?
- 原抽象能否支撑新场景,还是一迁移就漏出场景耦合?

## 最终产出

- `transfer_report.md`
- `final_reuse_assessment.md`
- 对“什么才算学会 Agent 工程”的一版清晰标准
