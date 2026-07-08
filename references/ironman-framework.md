# Ironman Series Framework

## Purpose

Use this reference to plan a 30-day technical writing series modeled on a successful "concept to system" structure: introduce a timely technical domain, teach its primitives, combine them into patterns, add production concerns, and finish with an integrated demo.

## Pattern Extracted From The Reference Series

The successful structure is not "30 independent tutorials." It is a cumulative system-building path:

```text
Days 1-3: define the field, motivation, terminology, and map
Days 4-10: teach core mechanics with small runnable examples
Days 11-17: introduce design patterns and multi-part workflows
Days 18-20: add engineering support such as memory, observability, or persistence
Days 21-25: apply the core ideas to advanced use cases
Days 26-28: survey supporting ecosystem tools
Days 29-30: wrap the system with API/UI/full-stack integration
```

The reader should feel that each article adds a new capability to the same long-running project.

## Topic Selection Rubric

Score each item 1-5. Prefer topics scoring 22+ out of 30.

```text
1. Timeliness: is the topic clearly relevant this year?
2. Depth: can it sustain 30 days without filler?
3. Buildability: can each week include runnable code or artifacts?
4. Narrative: does it naturally progress from basics to system?
5. Differentiation: is it more specific than generic API usage?
6. Final demo: can Day 30 show a concrete, integrated result?
```

Strong topic shapes:

```text
Use X to build Y system
From zero to production-grade Y with X
Engineering Y agents/apps/workflows with X
Building a local-first / observable / evaluated / deployable Y
```

Weak topic shapes:

```text
30 days learning one API
30 AI tools in 30 days
Prompt tricks without a system
Theory-only survey
Daily notes without a final project
```

## The Day 30 Backcast

Before writing Day 1, define:

```text
Final artifact:
Primary user:
Input:
Output:
Core workflow:
Data or tools used:
UI/API surface:
Evaluation method:
What makes it non-trivial:
```

Then backcast:

```text
What must be true by Day 25 for the final demo to work?
What must be true by Day 20 for the advanced workflow to work?
What must be true by Day 15 for patterns to compose?
What must be true by Day 10 for readers to understand the primitives?
What must be true by Day 3 for readers to care?
```

## Default 30-Day Skeleton

Use this as the first draft, then specialize it to the user's topic.

```text
Day 1: Why this topic matters now, and what we will build
Day 2: Core concepts and terminology
Day 3: System architecture and 30-day roadmap

Day 4: Environment setup and first minimal example
Day 5: Streaming / event flow / interaction loop
Day 6: Tools, APIs, or external capabilities
Day 7: Routing and conditional logic
Day 8: State management
Day 9: Comparing this state model with familiar software patterns
Day 10: Project scaffold or visual development workflow

Day 11: Design pattern overview
Day 12: Reflection / critique / feedback loop
Day 13: Revision with memory or iterative improvement
Day 14: Domain-specific workflow example
Day 15: Planning / task decomposition
Day 16: Collaboration / parallel workers / multi-module system
Day 17: Supervisor / orchestration pattern

Day 18: Observability and tracing
Day 19: Memory and persistence
Day 20: Database or durable storage integration

Day 21: Retrieval or data-grounded workflow
Day 22: Corrective or quality-control layer
Day 23: Adaptive routing based on task complexity
Day 24: Graph or relational knowledge layer
Day 25: Domain case study combining the advanced pieces

Day 26: Local model / alternative runtime / cost control
Day 27: Optimization framework or evaluation toolkit
Day 28: Benchmarking, testing, or prompt/program optimization

Day 29: Backend API and service interface
Day 30: UI, full integration, final demo, and lessons learned
```

## Per-Article Template

Use this for every article:

```text
Title:
Today we solve:
Where this fits in the final system:
Concept diagram:
Minimal runnable example:
Code walkthrough:
Design tradeoffs:
Common failure modes:
What changed in the project after today:
Tomorrow's bridge:
```

For shorter articles, keep all headings but compress sections. Continuity matters more than length.

## Companion Repo Structure

Prefer a repo that reflects the learning path and still supports a final product.

```text
README.md
notebooks/
  day01-...
  day02-...
examples/
  minimal/
  patterns/
src/
  core/
  workflows/
  tools/
  storage/
  evaluation/
apps/
  api/
  web/
docs/
  architecture.md
  roadmap.md
data/
  sample/
```

For early-stage tutorial repos, notebooks are acceptable. By the final week, add package-style code, API, and UI folders so the work feels like a system.

## Article Title Rules

Good titles should contain:

```text
The concrete capability
The technical frame
The reader outcome
```

Examples:

```text
從零建立可觀測的 AI 工作流：把追蹤資料接進系統
讓代理學會判斷資料夠不夠：Corrective RAG 的實作
把研究助理包成服務：FastAPI 與 Streamlit 的最後一哩
```

Avoid:

```text
Day 5 學習某套件
今天來玩某 API
某工具介紹
```

## Award-Oriented Quality Heuristics

These are planning heuristics, not guarantees.

```text
Novelty: topic feels current and specific
Continuity: articles visibly build toward one system
Reproducibility: code and repo allow readers to follow
Practicality: examples solve recognizable problems
Depth: advanced days include tradeoffs, not only demos
Communication: diagrams and explanations reduce cognitive load
Completion: Day 30 has an integrated artifact
```

## Common Failure Modes

```text
Tool parade: each day introduces a new library with no throughline
Notebook trap: everything stays in notebooks and never becomes a system
Theory cliff: early days over-explain concepts before readers see output
Demo cliff: final project appears suddenly in Day 29 without gradual build-up
No evaluation: claims of "better" without tests, metrics, traces, or examples
No reader identity: beginner and advanced readers are both poorly served
```

## Recommended Response Style

When asked to plan, be concrete:

```text
I would position this as...
The Day 30 artifact should be...
The risky part is...
Here is the 30-day arc...
Here is the repo structure...
```

When asked to critique, be direct:

```text
This topic is too broad because...
The final demo is not yet strong enough because...
Days X-Y feel like filler; combine them and use the room for...
```
