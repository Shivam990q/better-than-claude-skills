# Contributing to Better Than Claude Skills

First off, **thank you** for considering contributing! 🎉 Every skill, bug fix, and improvement helps the entire AI community.

<br>

## 🚀 Quick Ways to Contribute

| Type | Description |
|------|-------------|
| 🐛 **Bug Fix** | Found a skill that breaks? Fix it and submit a PR |
| ✨ **New Skill** | Built something useful? Add it to the arsenal |
| 📝 **Docs** | Improve documentation, fix typos, add examples |
| 🧪 **Testing** | Add evaluation test cases for existing skills |
| 🎨 **Design** | Improve README visuals, diagrams, or screenshots |

<br>

## 📋 Step-by-Step Guide

### 1. Fork & Clone

```bash
git clone https://github.com/YOUR_USERNAME/better-than-claude-skills.git
cd better-than-claude-skills
```

### 2. Create a Branch

```bash
git checkout -b feature/your-skill-name
# or
git checkout -b fix/what-you-fixed
```

### 3. Make Your Changes

If you're adding a **new skill**, follow this structure:

```
your-skill-name/
├── SKILL.md              # Core skill instructions (< 500 lines)
│   ├── YAML frontmatter  # Trigger definitions
│   └── Markdown body     # Workflow instructions
├── scripts/              # Executable Python/JS tools (optional)
├── references/           # Deep-dive docs (optional)
└── assets/               # Templates, fonts, icons (optional)
```

### 4. Skill Quality Checklist

Before submitting, make sure your skill meets these standards:

- [ ] **SKILL.md** is under 500 lines
- [ ] YAML frontmatter has clear trigger definitions
- [ ] Instructions use **Progressive Disclosure** (don't dump everything upfront)
- [ ] Scripts are self-contained and don't require system-level installs
- [ ] Tested with at least 3 different prompts
- [ ] No hardcoded API keys or secrets
- [ ] Includes at least one usage example

### 5. Commit & Push

```bash
git add .
git commit -m "feat: add your-skill-name skill"
git push origin feature/your-skill-name
```

### 6. Open a Pull Request

- Go to the [Pull Requests](https://github.com/shivam990q/better-than-claude-skills/pulls) tab
- Click **"New Pull Request"**
- Fill in the PR template
- Submit! 🎉

<br>

## 🏗️ Architecture Guidelines

### Progressive Disclosure is Non-Negotiable

Every skill **must** follow the 3-layer architecture:

1. **Layer 1 — Metadata** (always loaded): YAML frontmatter with triggers
2. **Layer 2 — Instructions** (loaded on activation): Main SKILL.md body
3. **Layer 3 — Resources** (loaded on demand): Scripts, references, assets

### Why?

- Keeps context windows lean
- Prevents hallucination from context overflow
- Ensures the AI loads only what it needs

<br>

## 🎯 Commit Convention

We use [Conventional Commits](https://www.conventionalcommits.org/):

| Prefix | Usage |
|--------|-------|
| `feat:` | New skill or feature |
| `fix:` | Bug fix in existing skill |
| `docs:` | Documentation updates |
| `refactor:` | Code restructuring |
| `test:` | Adding/updating tests |
| `chore:` | Maintenance tasks |

**Examples:**
```
feat: add kubernetes-deployment skill
fix: xlsx formula recalculation edge case
docs: improve frontend-design usage examples
```

<br>

## 💬 Got Questions?

- Open an [Issue](https://github.com/shivam990q/better-than-claude-skills/issues) with the `question` label
- Start a [Discussion](https://github.com/shivam990q/better-than-claude-skills/discussions)

<br>

## 🙏 Code of Conduct

By participating, you agree to abide by our [Code of Conduct](CODE_OF_CONDUCT.md). Be kind, be respectful, build cool stuff together.

---

<div align="center">

**Every contribution makes LLMs smarter for everyone.** 🚀

</div>
