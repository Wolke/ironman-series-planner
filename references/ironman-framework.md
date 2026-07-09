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

## Execution Evidence And Screenshots

When an article includes a real tool workflow, the article should preserve the run as evidence, not only describe it. This matters for UI builders, AI coding tools, deployment dashboards, analytics panels, generated previews, GitHub pages, and any step where the reader benefits from seeing the actual state transition.

Recommended placement:

```text
Prompt or command
Execution screenshots
Concept diagram
Verification
```

For example, if a day asks the reader to paste a prompt into Lovable, put the screenshots immediately after the prompt block. The reader should see: the prompt entry, any login or permission gate, the submitted/generating state, and the final response or generated artifact.

Screenshot naming:

```text
docs/ironman/screenshots/day02-lovable/
  day02-01-lovable-home.png
  day02-02-prompt-entered.png
  day02-03-login-required.png
  day02-04-dashboard-prompt-retained.png
  day02-05-project-generating.png
  day02-06-project-spec-ready.png
```

Use names that include:

```text
day number
zero-padded step number
actual observed state
```

Avoid vague names:

```text
after-submit.png
screenshot1.png
final.png
```

Good screenshot captions should explain what changed, not merely restate the file name:

```md
5. 送出後，Lovable 建立 `Nail Studio Hub` project，開始整理規格。

![Lovable 建立 project 並開始生成](../screenshots/day02-lovable/day02-05-project-generating.png)
```

GitHub visibility checklist:

```text
1. Confirm the Markdown relative path resolves from the article file location.
2. Confirm the image file is not ignored by .gitignore.
3. Stage both the Markdown file and the image files.
4. Commit and push before checking GitHub's rendered view.
5. If raw.githubusercontent.com returns 404 for a private repo, verify with authenticated `gh api` instead of assuming the file is missing.
6. Refresh the rendered GitHub page after push; a local preview is not enough.
7. Check at least one pushed screenshot asset directly, not only the Markdown diff.
```

Common failure mode: adding image links to the article but forgetting to commit the PNG files. The Markdown can be correct and still show broken images on GitHub because the assets only exist in the local working tree.

Field lesson from a Lovable Day 2 run:

```text
Symptom: the article opens on GitHub, but the embedded screenshots are invisible.
Do not diagnose this as only a link problem.
Check the whole delivery chain:
1. The screenshot files are inside the repo, under the article area's stable screenshot folder.
2. The Markdown link is relative to the article file, not relative to the repo root or the browser URL.
3. The file names are stable, ordered, and descriptive enough to survive review.
4. The PNG files are staged, committed, pushed, and present on GitHub.
5. The rendered GitHub page is refreshed after push and checked visually.
6. The same Markdown file also renders when opened directly from the local workspace.
```

Local Markdown visibility checklist:

```text
1. Open the article file itself, not only the repository root or GitHub page.
2. Resolve every image path from the article file's directory.
3. For `docs/ironman/articles/day02.md`, the screenshot folder is `../screenshots/day02-lovable/`, not `docs/ironman/screenshots/day02-lovable/`.
4. If the local article preview cannot show the image, fix the path before checking GitHub.
5. After any rename, update the Markdown and remove or ignore stale temporary files.
6. Do not use root-relative repo paths, GitHub blob URLs, or raw URLs for local article screenshots unless the publishing target explicitly requires them.
```

End-to-end screenshot delivery checklist:

```text
1. Capture the actual UI state that proves the step, not a nearby or convenient screen.
2. Save it under `docs/ironman/screenshots/dayXX-tool/`.
3. Rename it before embedding: `dayXX-SS-short-observed-state.png`.
4. Embed it near the prompt, command, or workflow step it proves.
5. Preview the article locally from `docs/ironman/articles/dayXX.md`.
6. Run repository validation if available.
7. Stage the article and PNG files together.
8. Commit and push.
9. Verify a pushed asset exists with authenticated GitHub tooling when the repo is private.
10. Re-open or refresh the rendered article and confirm the image is visible.
```

Screenshot file naming should survive a later review without extra context. Prefer names that answer "which day, which step, what UI state":

```text
day02-01-lovable-dashboard-ready.png
day02-02-product-brief-prompt-entered.png
day02-03-product-brief-generating.png
day02-04-product-brief-response-ready.png
```

Avoid names that hide the workflow state or came from the capture tool:

```text
截圖 2026-07-09 上午9.16.09.png
Google Chrome Appshot 2026-07-09T09-16-09.246Z.png
lovable.png
result.png
wrong-link-fixed.png
```

For a prompt-to-builder article, the screenshot sequence should preserve the reader's trust in the actual run:

```text
dayXX-01-prompt-entered.png
dayXX-02-submitted-or-generating.png
dayXX-03-response-ready.png
dayXX-04-generated-preview.png
```

If the workflow has two phases, name the phase explicitly:

```text
day07-01-plan-prompt-entered.png
day07-02-plan-generating.png
day07-03-plan-response-ready.png
day07-04-build-prompt-entered.png
day07-05-booking-form-generating.png
day07-06-booking-form-preview.png
```

Avoid names that were meaningful only during capture:

```text
download.png
Screenshot 2026-07-09 at 10.12.33.png
debug-input-state.png
lovable-final.png
```

Only keep debug screenshots if the article explicitly teaches debugging. Otherwise delete them before commit so the screenshot folder reads like a walkthrough, not a capture dump.

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
