---
name: orient
description: Four-pass orientation framework for exploring unfamiliar codebases, documentation, or complex systems. Use when Jillian is about to dive into something new and wants to avoid getting lost. Separates discovery from learning to reduce cognitive load.
---

# Orient: Four-Pass Framework

Use this skill when Jillian is about to explore something unfamiliar — a new codebase, a docs site, an API, a complex system, or a planning task with unclear scope. The goal is to build a stable mental map before any learning happens.

**Core law: never combine exploration, explanation, and organization in the same pass.**

---

## PASS 0 — Mode Check

Before starting, ask two questions:

1. **What are we orienting in?**
   - A codebase (local files)
   - A documentation site (URL)
   - A concept or system (described in text)
   - A planning task (figuring out what we have before deciding what to do)

2. **What output format works best right now?**
   - Text list (fastest, most editable)
   - Mermaid mindmap (good for visual overview)
   - Table (good for comparison)

Do not start PASS 1 until both are answered.

---

## PASS 1 — Inventory Only

**Mode: exploration. No understanding allowed.**

Extract the raw structure of what exists. The goal is visibility, not meaning.

For a **codebase**:
- Top-level directories and what they contain (one level deep)
- Key config files (package.json, pyproject.toml, CLAUDE.md, etc.)
- Entry points (main files, index files, CLI scripts)
- Test locations

For **documentation**:
- Navigation sections (left sidebar or top nav)
- Pages under each section (titles only)
- Any right-side page outlines (if accessible)

For a **planning task**:
- List what is known (confirmed facts, existing files, stated constraints)
- List what is unknown (questions that need answering before acting)
- List what is assumed (things being treated as true without confirmation)

**Output rules:**
- No explanations
- No merging of similar items
- No implied hierarchy beyond what actually exists
- Boring is correct — "this looks like a lot" is a sign of success, not failure

---

## PASS 2 — Flatten Structure

**Mode: organization. No new discovery, no explanation.**

Take the PASS 1 inventory and render it in the chosen format.

**Mermaid mindmap** (recommended default):
```
mindmap
  root((Project Name))
    src
      components
      utils
      hooks
    tests
    config
      package.json
      tsconfig.json
```

**Table** (good when comparing sections):
| Section | Pages | Notes |
|---------|-------|-------|
| Getting Started | Install, Quickstart, Config | — |
| Reference | API, CLI, Types | — |

**Rules:**
- Show containment, not importance
- Do not reorder items to imply priority
- Do not add categories that weren't in PASS 1
- Label the output clearly: "This is structure only — no meaning implied"

---

## PASS 3 — Concept Index (optional)

**Mode: classification. One letter per item. No notes yet.**

Tag each item from the inventory with one letter:

| Tag | Meaning | Examples |
|-----|---------|---------|
| **C** | Concept — a noun, a thing that exists | User, Token, Schema, Model |
| **O** | Operation — a verb, something you can do | Create, Query, Authenticate, Deploy |
| **I** | Interface — where it happens | Dashboard, CLI, API endpoint, Config file |
| **U** | Use case — why you'd care | Onboarding flow, Bulk import, Admin view |

**Rules:**
- One letter only — no explanations yet
- If something could be two, pick the most dominant one
- Unknown = mark with `?` and keep moving

This pass typically reduces cognitive load by ~60% by removing the "what IS this?" question from the "what do I do with it?" question.

---

## PASS 4 — Learning Selection

**Mode: decision. Now we choose what to actually engage with.**

Based on Jillian's specific goal for this session, identify:

1. **The 3–5 items that matter most right now** — and why
2. **Everything else** — explicitly named as "out of scope for now" (not deleted, just parked)
3. **The first concrete step** — one action, not a plan

Present as:
```
Focus now:
- [Item A] — because [one-line reason]
- [Item B] — because [one-line reason]
- [Item C] — because [one-line reason]

Parked (not lost):
- [Item D], [Item E], [Item F]

First step: [single concrete action]
```

---

## Closing: Universal Intake Prompt

At the end of the orient session, offer this reusable prompt Jillian can use independently in any AI tool:

```
I am not trying to learn this yet.

Create a navigation inventory of [this codebase / these docs / this system]:
- Top-level structure
- What exists under each section
- Entry points and key files

Do not explain concepts. Do not merge duplicates. Do not impose order or hierarchy.

This is for orientation only.
```

---

## Emergency Reset

If Jillian gets overwhelmed at any point during any pass:

> "You're not supposed to understand this yet. We're just figuring out what exists."

Pause. Return to the last completed pass. Ask what to do next.
