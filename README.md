# Agent Guidance

A project-driven learning path for building production-grade LLM Agent systems — from a bare Agent Loop to a full Multi-Agent research assistant.

## What This Is

This repo contains a structured 6-week learning plan designed around one principle: **build a real system, not a demo**. Every week ships a working increment of [ResearchAgent](#researchagent) — a personal research assistant that evolves as new Agent capabilities are added.

## Learning Path

| Week | Dates | Core Capability | Deliverable |
|---|---|---|---|
| Week 01 | Apr 20 – Apr 26 | Agent Loop · Tool System (start) | Runnable Agent Loop + Tool Registry |
| Week 02 | Apr 27 – May 03 | Tool System (complete) · MVP | ResearchAgent MVP |
| Week 03 | May 04 – May 10 | Memory System | 4-type memory + AutoDream |
| Week 04 | May 11 – May 17 | Planning System | Planner + Executor + Replanner |
| Week 05 | May 18 – May 24 | Multi-Agent (foundations) | Coordinator + 3 Worker types |
| Week 06 | May 25 – May 31 | System Integration + Observability | Complete ResearchAgent |

## ResearchAgent

The through-line project. A personal research assistant that grows in capability each week:

```
Week 02  Single Agent + 6 tools + CLI
Week 03  + 4-type memory (user/feedback/project/reference) + cross-session persistence
Week 04  + Planner-Executor separation + dynamic Replanning + Token budget control
Week 06  + Coordinator/Worker multi-agent + Cost Tracking + Trace/Span observability
```

**Example capability (Week 06):**
> "Compare 5 major Agent frameworks and generate a deep analysis report"
> → 3 Searcher Workers run in parallel → Coordinator synthesizes → Writer Workers draft sections → output in < 3 minutes, no human intervention

## Design Principles

**Permission-First** — Every tool defaults to denied. `needs_permission()` returns `allow | deny | ask_user`.

**Memory-as-Index** — Memory is a retrieval system, not a context dump. The index (< 1000 tokens) is always loaded; payloads are fetched on demand.

**Coordinator-Worker Pattern** — Multi-Agent is not peer-to-peer. The Coordinator owns synthesis (never delegated); Workers receive self-contained prompts with no access to Coordinator history.

**Cost-as-First-Class-Concern** — Token budgets and cost tracking are core infrastructure, not afterthoughts.

## Tech Stack

| Layer | Technology | Introduced |
|---|---|---|
| LLM calls | Anthropic SDK (direct) | Week 01 |
| Schema validation | Pydantic v2 | Week 01 |
| State machine | LangGraph | Week 04 |
| Search | Tavily API | Week 01 |
| Storage | Filesystem + SQLite | Week 01/03 |
| Observability | Custom Tracer + LangSmith (optional) | Week 06 |

> LangChain / AutoGen / CrewAI are intentionally excluded. Frameworks are only introduced once the underlying mechanism is understood by hand.

## Repository Structure

```
agent_learn_guidance.md      ← Original roadmap evaluation (roadmap.sh + Claude Code leak analysis)
Agent-Learning/
  INDEX.md                   ← Learning path overview with Mermaid diagram
  Week-01_2026-04-20.md
  Week-02_2026-04-27.md
  Week-03_2026-05-04.md
  Week-04_2026-05-11.md
  Week-05_2026-05-18.md
  Week-06_2026-05-25.md
```

## Background

The roadmap evaluation in `agent_learn_guidance.md` analyzes [roadmap.sh/ai-agents](https://roadmap.sh/ai-agents) and draws on architectural insights from the Claude Code source leak (March 2026) — particularly around the QueryEngine, 4-type memory system, Coordinator/Worker pattern, and cost tracking.

The core critique: most learning resources teach Agent *concepts* but not Agent *engineering*. This plan closes that gap by building a system you'd actually use.
