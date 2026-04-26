---
title: Agent Learning — 学习路径总览
tags:
  - agent-learning
  - index
aliases:
  - Agent学习总览
status: active
created: 2026-04-20
updated: 2026-04-24
---

# Agent Learning — 学习路径总览

这套笔记采用**双层结构**:

- **能力视图**:按主题学习,适合建立认知框架、回顾设计原则、横向对比方案
- **时间视图**:按周推进,适合执行计划、控制节奏、记录交付与复盘

> [!tip] 如何使用这套结构
> - 如果你要**学一个主题**:从下面的「能力地图」进入
> - 如果你要**看本周该做什么**:从下面的「时间视图」进入
> - 如果你要**复盘一条主线是否真的成立**:优先看主题页,再回跳到对应周次的证据与交付

---

## 能力地图

### 基础骨架

- [[Agent-Learning/Topics/Agent-Loop|Agent Loop]]
- [[Agent-Learning/Topics/Tool-System|Tool System]]
- [[Agent-Learning/Topics/LLMClient|LLMClient / Provider 抽象]]

### 验证与工程化

- [[Agent-Learning/Topics/Eval-Harness|Eval Harness / Baseline]]
- [[Agent-Learning/Topics/Observability|Observability / Cost / Trace]]
- [[Agent-Learning/Topics/Reuse-Transfer|Reuse / Transfer]]

### 核心智能能力

- [[Agent-Learning/Topics/Memory|Memory]]
- [[Agent-Learning/Topics/Planning|Planning]]
- [[Agent-Learning/Topics/Reflection|Reflection]]

### 架构决策

- [[Agent-Learning/Topics/ReAct-vs-PlanAct|ReAct vs Plan-Act]]
- [[Agent-Learning/Topics/Multi-Agent-vs-Routing|Multi-Agent vs Routing]]

---

## 时间视图

| 周次 | 日期 | 阶段 | 主要目标 |
|---|---|---|---|
| [[Agent-Learning/Week-01_2026-04-20|Week 01]] | 04-20 ~ 04-26 | 阶段0+1 | Agent Loop 跑通 + Tool System 启动 |
| [[Agent-Learning/Week-02_2026-04-27|Week 02]] | 04-27 ~ 05-03 | 阶段1 | MVP + LLMClient + Reflection 雏形 + Eval Harness |
| [[Agent-Learning/Week-03_2026-05-04|Week 03]] | 05-04 ~ 05-10 | 阶段2 | Memory System + 数据驱动必要性验证 |
| [[Agent-Learning/Week-04_2026-05-11|Week 04]] | 05-11 ~ 05-17 | 阶段3 | Planning + LangGraph + Reflection 闭环 + ReAct 对比 |
| [[Agent-Learning/Week-05_2026-05-18|Week 05]] | 05-18 ~ 05-24 | 阶段4上 | Multi-Agent 必要性证伪 / 模型路由 + Chaos |
| [[Agent-Learning/Week-06_2026-05-25|Week 06]] | 05-25 ~ 05-31 | 阶段4下 | 工业化 + 横向迁移 + 最终交付 |

---

## 三个项目视角

不是只做一个 demo,而是从三个角度验证抽象是否成立。

| 项目 | 角色 | 作用 | 核心判断 |
|---|---|---|---|
| **ResearchAgent** | 主项目 | 验证完整能力栈 | 是否能把 Tool / Memory / Planning / Reflection 串成端到端系统 |
| **CodeReviewAgent** | 第二项目 | 验证基础设施复用度 | 是否做到复用率 ≥ 80%,新增代码 < 500 行 |
| **DataAnalysisAgent** | 第三项目 | 验证抽象层领域无关 | 是否能在 90 分钟内迁移出最小可用版本 |

---

## 贯穿问题

学习过程中反复回答这 6 个问题:

1. 当前新能力是否真的必要,还是只是炫技?
2. 这个能力是局部技巧,还是可复用基础设施?
3. 是否有 baseline 能证明它比上一阶段更好?
4. 如果失败,失败原因是 Prompt、架构还是评估方式?
5. 这个抽象能否迁移到第二、第三个项目?
6. 如果现在重来,这一层还会不会这样设计?

---

## 建议阅读顺序

### 第一次走完整体

1. 先读 [[Agent-Learning/Topics/Agent-Loop|Agent Loop]]
2. 再读 [[Agent-Learning/Topics/Tool-System|Tool System]] + [[Agent-Learning/Topics/LLMClient|LLMClient]]
3. 然后读 [[Agent-Learning/Topics/Eval-Harness|Eval Harness]]
4. 再进入 [[Agent-Learning/Topics/Memory|Memory]] / [[Agent-Learning/Topics/Planning|Planning]] / [[Agent-Learning/Topics/Reflection|Reflection]]
5. 最后读 [[Agent-Learning/Topics/ReAct-vs-PlanAct|ReAct vs Plan-Act]] 与 [[Agent-Learning/Topics/Multi-Agent-vs-Routing|Multi-Agent vs Routing]] 两个决策页

### 复盘时

- 想看执行节奏:回到对应 Week note
- 想看某条能力线有没有形成体系:回到对应 Topic note
- 想看是否真的抽象成功:直接看 [[Agent-Learning/Topics/Reuse-Transfer|Reuse / Transfer]]

---

## 原周计划索引

保留 week notes,因为它们仍然适合做执行与复盘。

- [[Agent-Learning/Week-01_2026-04-20|Week 01]]
- [[Agent-Learning/Week-02_2026-04-27|Week 02]]
- [[Agent-Learning/Week-03_2026-05-04|Week 03]]
- [[Agent-Learning/Week-04_2026-05-11|Week 04]]
- [[Agent-Learning/Week-05_2026-05-18|Week 05]]
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]

---

## 参考

- [[agent_learn_guidance|原始路线图评估]]
