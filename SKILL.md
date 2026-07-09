---
name: ironman-series-planner
description: Plan, critique, and structure an iThome Ironman-style 30-day technical article series using an award-oriented framework. Use when the user wants to create a new Ironman topic, reverse-engineer a successful series, design a 30-day article roadmap, define a final demo/product, build a companion GitHub repository structure, improve award chances, or turn a technical idea into a progressive tutorial series.
---

# Ironman Series Planner

## Overview

Use this skill to turn a technical topic into a coherent 30-day series with a visible learning arc, executable demos, and a final integrated project. Optimize for a reader-followable technical narrative, not isolated daily notes.

Read [references/ironman-framework.md](references/ironman-framework.md) when planning a full series, evaluating a topic, creating the 30-day outline, or designing the repo/final demo.

## Core Workflow

1. Start from the Day 30 artifact.
   Define the final system, demo, or deliverable before listing article titles. A strong series should accumulate toward something concrete.

2. Identify the technical spine.
   State the central framework, domain, or system pattern that connects all 30 days. Avoid a topic that is only a collection of unrelated tools.

3. Split the series into four arcs.
   Use this default arc unless the user's topic requires a different pacing:
   - Days 1-3: problem framing, landscape, final target
   - Days 4-10: core concepts and minimal runnable examples
   - Days 11-17: design patterns and composable modules
   - Days 18-25: production concerns and advanced applications
   - Days 26-30: ecosystem, integration, UI/API/deployment, retrospective

4. Make every day produce progress.
   Each article must add at least one of: concept, code module, evaluation method, data asset, architecture decision, integration point, or final-system capability.

5. Design the companion repository.
   Mirror the article progression in folders. Include notebooks or runnable examples for early days, then package/API/UI structure near the end.

6. Add award-oriented polish.
   Check for novelty, continuity, runnable code, diagrams, reproducibility, engineering realism, and a clear final demo.

7. Capture real execution evidence when the article describes a tool run.
   If the article asks the reader to paste a prompt, run a builder, publish, deploy, inspect analytics, or otherwise operate an external UI, treat screenshots as part of the artifact. Add them to the companion repo with stable names, embed them in the article near the relevant prompt or command, and verify the images are visible from the rendered destination after commit/push.

8. Treat screenshot repair as article repair, not asset cleanup.
   If a rendered article does not show the image, fix the article and repository state together: confirm the relative path from the Markdown file, rename vague or misplaced screenshots, stage the PNG files with the Markdown change, push, and re-open the rendered page. Do not stop at "the file exists locally."

9. Verify local Markdown rendering before calling the article done.
   A reader may open `docs/ironman/articles/dayXX.md` directly in an editor or local Markdown viewer. Image links must therefore be relative to the article file's directory and should render locally before relying on GitHub's rendered page. If local preview cannot show the image, fix the Markdown path or asset location first.

10. Preserve the screenshot delivery chain.
   For every screenshot-backed article, keep the chain intact: capture the real UI state, save the PNG under the repo, name it with day/step/state, link it from the article using the article-relative path, stage the Markdown and PNGs together, commit, push, and verify the pushed file exists. A broken image is usually a chain failure, not only a Markdown typo.

11. Name screenshots for later review, not for the capture moment.
   Avoid OS/browser/appshot names and temporary debugging labels. Use names that answer "which day, which step, what state did the reader see?" such as `day02-03-product-brief-generating.png` or `day07-06-booking-form-preview.png`. If the filename needs the surrounding chat to make sense, rename it before embedding.

## Output Shapes

For a topic proposal, produce:

```text
Topic:
Positioning:
Final Day 30 Demo:
Target Reader:
Why This Is Timely:
Risk:
Suggested Series Arc:
```

For a full 30-day plan, produce a table with:

```text
Day | Article title | Reader promise | Demo/code artifact | How it advances the final project
```

For a repo plan, produce:

```text
README.md
notebooks/
src/
apps/
services/
examples/
docs/
```

Adjust folder names to the selected stack and avoid over-engineering early prototypes.

## Quality Gate

Before finalizing any plan, verify:

- The Day 30 artifact is specific enough to demo.
- Days 1-10 teach foundations without becoming pure theory.
- Days 11-20 introduce reusable patterns, not only feature increments.
- Days 21-30 demonstrate engineering maturity: evaluation, observability, persistence, deployment, UI, or operational tradeoffs.
- The series has a visible narrative: each day answers "why now, why this step, what changed in the system?"
- The topic is not just "30 days of API calls" or "30 AI tools in 30 days."
- Any screenshots or generated assets referenced by an article are committed, pushed, and visible in the rendered Markdown destination, not only present in the local working tree.
- Screenshot file names identify the day, step order, and observed UI state; avoid browser-download names, generic names, spaces, and names that only make sense outside the repo.
- A direct local open of the article Markdown shows the screenshots. In `docs/ironman/articles/day02.md`, a link to `docs/ironman/screenshots/...` is wrong because it is repo-root-relative; from the article file, use `../screenshots/day02-lovable/...`.
- Each screenshot section sits close to the prompt, command, or workflow it proves. Do not collect screenshots only at the end of the article unless the article itself is a retrospective.
- The screenshot folder contains only narrative evidence for the article. Remove stray capture attempts, stale renamed files, and debug images unless the article explicitly discusses them.
- Remote verification checks the pushed asset, not only the page text. For private GitHub repos, use authenticated GitHub tooling such as `gh api repos/OWNER/REPO/contents/PATH --jq .size` when raw unauthenticated URLs are inconclusive.

## Tone And Framing

Prefer pragmatic, technical, and reader-respecting writing. Use concrete system names, diagrams, code artifacts, and tradeoffs. Avoid award-gaming language in the actual article titles; keep the award strategy internal to planning.
