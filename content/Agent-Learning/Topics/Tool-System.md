---
title: Tool System
tags: [agent-learning, topic, tools]
status: active
---

# Tool System

## 这页回答什么

如何把工具做成一个可扩展、可控、可验证的系统,而不是一堆散落函数。

## 核心组成

- `BaseTool`
- `InputSchema`
- `ToolRegistry`
- Permission Model
- Feature Flag
- HITL

## 关键设计原则

- Permission-First
- 新增工具默认低改动接入
- 高风险工具显式确认
- 关闭工具要通过配置而不是删代码

## 对应周次

- [[Agent-Learning/Week-01_2026-04-20|Week 01]]:统一接口、注册表、权限三态、黑名单 flag
- [[Agent-Learning/Week-02_2026-04-27|Week 02]]:新增高风险工具、并发调用、Schema 自纠
- [[Agent-Learning/Week-06_2026-05-25|Week 06]]:`run_python` 真正沙箱化

## 验证标准

- 新增一个工具不需要修改 Agent Loop
- 某工具被禁用后不再暴露给 LLM
- 参数非法时能把结构化错误回给 LLM 自纠
- 高风险工具具备确认机制

## 学习重点

工具不是 API 包装,而是 Agent 的可控执行边界。
