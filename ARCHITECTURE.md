# Architecture — Progressive Disclosure System

<div align="center">

### How Better Than Claude Skills achieves zero-hallucination, context-efficient AI execution

</div>

<br>

## 🧠 The Problem

Modern LLMs have a **context window problem**:

- Stuff too much information → the AI loses focus and hallucinates
- Provide too little → the AI makes assumptions and produces generic output
- No structure → the AI doesn't know *when* to use *what*

Traditional prompt engineering treats every interaction as a blank slate. That's fundamentally broken for complex, multi-step workflows.

<br>

## 💡 The Solution: Progressive Disclosure Architecture

Every skill in this repository is built on a **3-layer architecture** inspired by how human experts work — they don't load their entire education into working memory for every task. They recall what's needed, when it's needed.

```
┌─────────────────────────────────────────────────┐
│                                                 │
│   LAYER 1 — METADATA (Always Present)           │
│   ┌───────────────────────────────────────┐     │
│   │  YAML Frontmatter                     │     │
│   │  • Skill name & description           │     │
│   │  • Trigger conditions                 │     │
│   │  • Activation keywords                │     │
│   │  • Version & compatibility            │     │
│   └───────────────────────────────────────┘     │
│                     ↓                           │
│   LAYER 2 — INSTRUCTIONS (On Activation)        │
│   ┌───────────────────────────────────────┐     │
│   │  SKILL.md Body                        │     │
│   │  • High-level workflow steps          │     │
│   │  • Decision trees & branching logic   │     │
│   │  • Quality gates & checkpoints        │     │
│   │  • Error handling patterns            │     │
│   └───────────────────────────────────────┘     │
│                     ↓                           │
│   LAYER 3 — RESOURCES (On Demand)               │
│   ┌───────────────────────────────────────┐     │
│   │  scripts/    → Executable tools       │     │
│   │  references/ → Deep documentation     │     │
│   │  assets/     → Templates & media      │     │
│   └───────────────────────────────────────┘     │
│                                                 │
└─────────────────────────────────────────────────┘
```

<br>

## 🔍 Layer Details

### Layer 1 — Metadata (Always Loaded)

The YAML frontmatter acts as a **"pushy" trigger system**. It sits in the AI's context at all times and activates when the user's request matches certain patterns.

```yaml
---
name: frontend-design
description: Generate production-grade frontend interfaces
triggers:
  - "build a website"
  - "create a landing page"
  - "design a UI"
  - "frontend"
version: 1.0.0
---
```

**Cost:** ~50-100 tokens per skill (negligible)

### Layer 2 — Body Instructions (On Activation)

When triggered, the AI reads the `SKILL.md` body — a lightweight orchestrator that tells it **how** to approach the task.

Key principles:
- Under 500 lines (strict limit)
- Uses decision trees, not monolithic instructions
- Includes quality gates and verification steps
- References Layer 3 resources by name (loaded only if needed)

**Cost:** ~500-2000 tokens (loaded once per task)

### Layer 3 — Bundled Resources (On Demand)

Heavy resources — scripts, reference docs, templates — are **never** pre-loaded. The AI pulls them into context only when a specific workflow step requires them.

```
scripts/
├── validate_output.py    # Loaded only during validation step
├── format_tables.js      # Loaded only for table formatting
└── generate_chart.py     # Loaded only for chart generation

references/
├── color-theory.md       # Loaded only for design decisions
├── api-reference.md      # Loaded only for API calls
└── edge-cases.md         # Loaded only for error handling
```

**Cost:** Variable — 0 tokens if not needed, loaded on demand

<br>

## 📊 Why This Works

| Approach | Context Usage | Hallucination Risk | Precision |
|----------|:------------:|:------------------:|:---------:|
| Raw prompting | 🔴 Unpredictable | 🔴 High | 🔴 Low |
| System prompts | 🟡 Fixed overhead | 🟡 Medium | 🟡 Medium |
| **Progressive Disclosure** | 🟢 **Minimal & adaptive** | 🟢 **Near zero** | 🟢 **Maximum** |

<br>

## 🔄 Skill Lifecycle

```
User Request
    │
    ▼
┌──────────────┐     No match
│ Layer 1 Scan │ ──────────────→ Normal AI response
│ (All skills) │
└──────┬───────┘
       │ Match found
       ▼
┌──────────────┐
│ Layer 2 Load │ ──→ Read SKILL.md body
│ (Activated)  │     Execute workflow steps
└──────┬───────┘
       │ Step needs resource
       ▼
┌──────────────┐
│ Layer 3 Pull │ ──→ Load specific script/reference
│ (On demand)  │     Execute, then release from context
└──────────────┘
```

<br>

## 🏗️ Building Skills with This Architecture

When creating a new skill, follow these constraints:

1. **SKILL.md must be under 500 lines** — if it's longer, move content to `references/`
2. **Scripts must be self-contained** — no system-level dependencies
3. **YAML triggers must be specific** — avoid false activations
4. **Layer 3 resources must be referenced by name** in Layer 2 instructions
5. **Each layer must function independently** — Layer 2 should work even if Layer 3 resources are unavailable

<br>

---

<div align="center">

*This architecture is what separates "prompt engineering" from "cognitive architecture for AI."*

</div>
