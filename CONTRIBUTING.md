# Contributing to Better Than Claude Skills

First off, **thank you** for considering contributing! 🎉 Every skill, bug fix, and improvement helps the entire AI community.

<br>

## 📑 Table of Contents

- [Quick Ways to Contribute](#-quick-ways-to-contribute)
- [Getting Started](#-getting-started)
- [Development Environment](#-development-environment)
- [Creating a New Skill](#-creating-a-new-skill)
- [Skill Quality Checklist](#-skill-quality-checklist)
- [Testing Your Skill](#-testing-your-skill)
- [Architecture Guidelines](#-architecture-guidelines)
- [Commit Convention](#-commit-convention)
- [Pull Request Process](#-pull-request-process)
- [Recognition](#-recognition)
- [FAQ](#-frequently-asked-questions)

<br>

## 🚀 Quick Ways to Contribute

| Type | Difficulty | Description |
|------|:----------:|-------------|
| 🐛 **Bug Fix** | 🟢 Easy | Found a skill that breaks? Fix it and submit a PR |
| 📝 **Docs** | 🟢 Easy | Improve documentation, fix typos, add examples |
| 🎨 **Design** | 🟢 Easy | Improve README visuals, diagrams, or screenshots |
| 🧪 **Testing** | 🟡 Medium | Add evaluation test cases for existing skills |
| ✨ **New Skill** | 🟡 Medium | Built something useful? Add it to the arsenal |
| 🏗️ **Architecture** | 🔴 Advanced | Improve the core Progressive Disclosure system |

<br>

## 🏁 Getting Started

### 1. Fork & Clone

```bash
# Fork the repo on GitHub first, then:
git clone https://github.com/YOUR_USERNAME/better-than-claude-skills.git
cd better-than-claude-skills
```

### 2. Create a Branch

```bash
# For new skills:
git checkout -b feat/your-skill-name

# For bug fixes:
git checkout -b fix/what-you-fixed

# For documentation:
git checkout -b docs/what-you-improved
```

### 3. Set Upstream

```bash
git remote add upstream https://github.com/shivam990q/better-than-claude-skills.git
git fetch upstream
```

<br>

## 🛠️ Development Environment

### Prerequisites

No mandatory tools — skills are plain text files. But for a better experience:

| Tool | Purpose | Required? |
|------|---------|:---------:|
| Git | Version control | ✅ |
| Python 3.9+ | Running evaluation scripts | Optional |
| Node.js 18+ | JavaScript-based skills/scripts | Optional |
| Claude Desktop / API | Testing skills in real AI environment | Recommended |

### Recommended Workflow

1. **Write your skill** → Use any text editor
2. **Test locally** → Load into Claude and test with real prompts
3. **Run evaluations** → Use the `skill-creator`'s built-in benchmarking (if applicable)
4. **Submit PR** → Follow the PR template

<br>

## ✨ Creating a New Skill

### Directory Structure

Every skill **must** follow this layout:

```
your-skill-name/
├── SKILL.md                  # Core skill instructions (REQUIRED, < 500 lines)
│   ├── YAML frontmatter      # Trigger definitions & metadata
│   └── Markdown body         # Workflow instructions
├── scripts/                  # Executable tools (optional)
│   ├── main.py               # Primary script
│   └── helpers.js            # Helper utilities
├── references/               # Deep-dive documentation (optional)
│   ├── api-reference.md      # External API docs
│   └── edge-cases.md         # Known edge cases & solutions
├── assets/                   # Templates, fonts, icons (optional)
│   ├── template.html         # Starter templates
│   └── config.json           # Default configurations
└── examples/                 # Usage examples (recommended)
    ├── basic-usage.md        # Simple use case
    └── advanced-usage.md     # Complex use case
```

### Naming Convention

| Rule | Example | Anti-Pattern |
|------|---------|:------------:|
| Use lowercase kebab-case | `pdf-merger` | `PDFMerger` ❌ |
| Be descriptive but concise | `webapp-testing` | `test` ❌ |
| Avoid generic names | `slack-gif-creator` | `gif-tool` ❌ |
| No version numbers in name | `mcp-builder` | `mcp-builder-v2` ❌ |

### YAML Frontmatter Template

```yaml
---
name: your-skill-name
description: One-line description of what this skill does
triggers:
  - "keyword phrase 1"
  - "keyword phrase 2"
  - "keyword phrase 3"
version: 1.0.0
author: Your Name
category: document | design | development | utility
platforms:
  - claude
  - gemini  # if compatible
---
```

<br>

## ✅ Skill Quality Checklist

Before submitting, verify **every** item:

### Structure & Size
- [ ] `SKILL.md` is under **500 lines** (hard limit)
- [ ] YAML frontmatter has **clear trigger definitions** (at least 3 triggers)
- [ ] Directory structure follows the standard layout
- [ ] No unnecessary files or bloat

### Architecture Compliance
- [ ] Instructions use **Progressive Disclosure** (don't dump everything upfront)
- [ ] Layer 3 resources are **referenced by name** in Layer 2 instructions
- [ ] Heavy content is in `references/` or `scripts/`, not in SKILL.md
- [ ] Skill works even if Layer 3 resources are unavailable (graceful degradation)

### Code Quality
- [ ] Scripts are **self-contained** — no system-level installs required
- [ ] All dependencies are documented in SKILL.md or a requirements file
- [ ] No hardcoded API keys, tokens, or secrets
- [ ] Scripts include error handling and informative error messages

### Testing
- [ ] Tested with at least **3 different prompts** of varying complexity
- [ ] Verified output quality matches or exceeds no-skill baseline
- [ ] Edge cases are documented and handled
- [ ] Includes at least one **usage example** in SKILL.md or `examples/`

### Documentation
- [ ] SKILL.md has a clear **"What it does"** section
- [ ] Workflow steps are numbered and logical
- [ ] External dependencies are listed
- [ ] Known limitations are documented

<br>

## 🧪 Testing Your Skill

### Manual Testing

1. Load your skill into Claude (or your target LLM)
2. Test with these prompt categories:

| Category | Example Prompt | What to Check |
|----------|----------------|---------------|
| **Basic** | Simple, direct request | Does it activate correctly? |
| **Complex** | Multi-step, specific requirements | Does it follow the full workflow? |
| **Edge Case** | Unusual input, missing info | Does it handle errors gracefully? |
| **Negative** | Unrelated request | Does it stay silent (no false activation)? |

### Automated Evaluation (Optional)

If your skill supports it, use the built-in evaluation framework:

```bash
# Using the skill-creator's evaluation pipeline
# Define test cases in evaluation_config.json
python scripts/evaluate.py --skill your-skill-name --cases 5
```

<br>

## 🏗️ Architecture Guidelines

### Progressive Disclosure is Non-Negotiable

Every skill **must** follow the 3-layer architecture:

1. **Layer 1 — Metadata** (always loaded): YAML frontmatter with triggers (~50-100 tokens)
2. **Layer 2 — Instructions** (loaded on activation): Main SKILL.md body (~500-2000 tokens)
3. **Layer 3 — Resources** (loaded on demand): Scripts, references, assets (variable)

### Why?

- **Context efficiency:** Keeps the AI's context window lean and focused
- **Zero hallucination:** AI only loads what it needs, when it needs it
- **Scalability:** Adding more skills doesn't degrade performance
- **Composability:** Skills can reference each other without conflict

### Common Mistakes to Avoid

| ❌ Don't | ✅ Do Instead |
|----------|--------------|
| Put everything in SKILL.md | Split into layers (instructions vs. references) |
| Use vague triggers like "help" | Use specific triggers like "create a landing page" |
| Hardcode file paths | Use relative paths or environment variables |
| Include inline scripts > 20 lines | Move to `scripts/` directory |
| Write monolithic instructions | Use decision trees with branching logic |

<br>

## 🎯 Commit Convention

We use [Conventional Commits](https://www.conventionalcommits.org/):

| Prefix | Usage | Example |
|--------|-------|---------|
| `feat:` | New skill or feature | `feat: add kubernetes-deployment skill` |
| `fix:` | Bug fix in existing skill | `fix: xlsx formula recalculation edge case` |
| `docs:` | Documentation updates | `docs: improve frontend-design usage examples` |
| `refactor:` | Code restructuring | `refactor: simplify pdf merge workflow` |
| `test:` | Adding/updating tests | `test: add evaluation cases for canvas-design` |
| `chore:` | Maintenance tasks | `chore: update .gitignore patterns` |
| `perf:` | Performance improvements | `perf: reduce skill-creator token usage` |

### Commit Message Format

```
<type>: <short description>

<optional longer description>

<optional footer: Fixes #123>
```

**Example:**
```
feat: add kubernetes-deployment skill

- Adds skill for generating K8s manifests, Helm charts, and kubectl commands
- Includes deployment, service, and ingress templates in references/
- Tested with 5 different cluster configurations

Fixes #42
```

<br>

## 🔄 Pull Request Process

### Before Submitting

1. ✅ Run through the **Skill Quality Checklist** above
2. ✅ Ensure your branch is up-to-date with `main`
3. ✅ Squash or clean up commit history if messy

### Review Process

| Step | Who | Timeframe |
|------|-----|-----------|
| PR submitted | You | — |
| Initial review | Maintainer | Within 48 hours |
| Feedback / changes requested | Maintainer → You | — |
| Changes made | You | — |
| Approval & merge | Maintainer | Within 24 hours of approval |

### What Reviewers Look For

1. **Architecture compliance** — Does it follow Progressive Disclosure?
2. **Code quality** — Are scripts clean, documented, and error-handled?
3. **Testing evidence** — Has it been tested with real prompts?
4. **Documentation** — Is it clear enough for a new contributor to understand?
5. **Security** — No hardcoded secrets, safe file operations?

<br>

## 🏆 Recognition

We believe in celebrating contributions:

- **All contributors** are added to the README's Contributors section
- **Significant skills** get a dedicated mention in CHANGELOG.md
- **Exceptional contributions** may be highlighted in project announcements and LinkedIn posts

<br>

## ❓ Frequently Asked Questions

**Q: Can I contribute a skill for a non-Claude LLM (e.g., Gemini, GPT)?**
> Yes! While this repo is optimized for Claude, many skills work across LLMs. Add a `platforms:` field in your YAML frontmatter to indicate compatibility.

**Q: My skill is over 500 lines — what do I do?**
> Move detailed content to `references/` and keep SKILL.md as a lightweight orchestrator. Think of SKILL.md as the "table of contents" and `references/` as the "chapters."

**Q: Can I modify an existing skill?**
> Absolutely. Fork, improve, test, and submit a PR. Just explain what you changed and why in the PR description.

**Q: Do I need to write tests?**
> Not mandatory, but strongly recommended. At minimum, include 3 tested prompts in your PR description.

**Q: How do I test without Claude?**
> You can review the SKILL.md logic manually and dry-run the workflow steps. For full testing, use Claude Desktop or the API.

<br>

## 💬 Got Questions?

- 🐛 Open an [Issue](https://github.com/shivam990q/better-than-claude-skills/issues) with the `question` label
- 💬 Start a [Discussion](https://github.com/shivam990q/better-than-claude-skills/discussions)
- 📧 Email the maintainer for private inquiries

<br>

## 🙏 Code of Conduct

By participating, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Be kind, be respectful, build cool stuff together.

---

<div align="center">

**Every contribution makes LLMs smarter for everyone.** 🚀

*Built by the community, for the community.*

</div>
