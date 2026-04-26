---
title: ReAct vs Plan-Act
tags: [agent-learning, topic, architecture-decision]
status: active
---

# ReAct vs Plan-Act

## 这页回答什么

两种范式分别适合什么任务,以及默认该选哪一个。

## 对应周次

- [[Agent-Learning/Week-04_2026-05-11|Week 04]]:首次 A/B 对比与决策报告
- [[Agent-Learning/Week-05_2026-05-18|Week 05]]:复杂任务下继续观察与继承

## 对比维度

- token
- latency
- judge score
- 步数
- 是否容易陷入局部试错
- 是否适合预先拆解的复杂任务

## 初步经验框架

- ReAct:步数少、探索性强、预先分解困难
- Plan-Act:复杂、可分解、需要预算控制与显式进度

## 最终输出

不是“哪个高级”,而是“默认范式如何选,例外条件是什么”。
