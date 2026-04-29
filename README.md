<div align="center">

# 🚀 Better Than Claude Skills

**Supercharge your AI assistants with 17+ highly-optimized, production-ready skills.**

[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=for-the-badge)](http://makeapullrequest.com)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![Maintenance](https://img.shields.io/badge/Maintained%3F-yes-green.svg?style=for-the-badge)](https://GitHub.com/Naereen/StrapDown.js/graphs/commit-activity)
[![Built with Love](https://img.shields.io/badge/Built_with-❤️-red.svg?style=for-the-badge)](#)

*Transform Claude, Gemini, and other LLMs into autonomous agents capable of generating algorithmic art, managing spreadsheets, co-authoring docs, and building complex web artifacts.*

<br/>

<table>
  <tr>
    <td align="center"><img width="1917" alt="Showcase 1" src="https://github.com/user-attachments/assets/53b6ddae-5004-43b6-87df-a0169067cfa0" /></td>
    <td align="center"><img width="1917" alt="Showcase 2" src="https://github.com/user-attachments/assets/eceefd01-75fd-4924-8287-7a154e76dda0" /></td>
  </tr>
  <tr>
    <td align="center"><img width="1919" alt="Showcase 3" src="https://github.com/user-attachments/assets/676edd16-1549-4084-889e-e61cd96c2de0" /></td>
    <td align="center"><img width="1919" alt="Showcase 4" src="https://github.com/user-attachments/assets/ee6be33e-e9f8-45be-ad88-355767f6fc8e" /></td>
  </tr>
</table>

</div>

---

## 📖 Table of Contents

- [✨ Why Use This Repository?](#-why-use-this-repository)
- [📦 Quick Start Installation](#-quick-start-installation)
- [🧰 The Skill Arsenal](#-the-skill-arsenal)
- [🏗️ Skill Architecture](#️-skill-architecture)
- [🛠️ Build Your Own Skills](#️-build-your-own-skills)
- [📊 Evaluation & Benchmarking](#-evaluation--benchmarking)
- [🤝 Contributing](#-contributing)

---

## ✨ Why Use This Repository?

Modern LLMs are incredibly smart, but they often lack the strict, domain-specific context needed to execute complex, multi-step workflows flawlessly. **Better Than Claude Skills** bridges that gap by providing:

- 🎯 **Pinpoint Accuracy:** Skills are designed with "Progressive Disclosure," meaning your AI only gets the context it needs, *when* it needs it.
- ⚡ **Zero-Friction Setup:** Pre-packaged `.skill` files are ready for immediate drag-and-drop deployment.
- 🛠️ **Autonomous Improvement:** Features a built-in `skill-creator` that allows your AI to autonomously write, benchmark, and optimize *new* skills for you.
- 🎨 **Production-Grade Outputs:** Generate visually stunning UI designs, beautiful generative art, and perfectly formatted corporate documents.

---

## 📦 Quick Start Installation

Getting started takes less than 60 seconds. You have two paths to power up your assistant:

### Option 1: Drag & Drop (Recommended)
The fastest way to enhance your AI interface.
1. Download or clone this repository.
2. Open the directory: `claude (skill-zip) to upload directly/`
3. Locate your desired `.skill` file (e.g., `frontend-design.skill`).
4. **Drag and drop** the file directly into your AI assistant interface! 🪄

### Option 2: Build & Package from Source
Perfect for developers looking to modify or inspect skills before deploying.
```bash
# 1. Navigate to the target skill directory
cd frontend-design/

# 2. Make your edits to SKILL.md, scripts, or references...

# 3. Use the built-in bundler to package your custom skill
python -m scripts.package_skill path/to/skill-folder
```

---

## 🧰 The Skill Arsenal

We've categorized our 17+ highly optimized skills to help you find exactly what you need. Click to expand each category!

<details>
<summary><b>📄 Document & Data Mastery</b></summary>
<br>

* **`docx` (word-processing):** Ultimate control over `.docx` files. Create, read, and manipulate Word documents with tables of contents, tracked changes, and flawless formatting.
* **`xlsx` (spreadsheet-processing):** Advanced spreadsheet manipulation. Read, fix, format, and generate `.xlsx`, `.xlsm`, `.csv`, or `.tsv` files effortlessly.
* **`pdf` (document-processing):** Comprehensive PDF operations. Extract text/tables, merge, split, watermark, encrypt, fill forms, and run OCR.
* **`pptx` (presentation-processing):** Create, edit, and extract content from professional `.pptx` presentation slides.
* **`doc-coauthoring`:** A structured, context-rich workflow for co-authoring technical documentation, proposals, and engineering specs.
</details>

<details>
<summary><b>🎨 Design & Visual Arts</b></summary>
<br>

* **`frontend-design`:** Generate distinctive, production-grade frontend interfaces with high design quality—say goodbye to generic AI aesthetics.
* **`algorithmic-art`:** Create stunning generative art using `p5.js` with seeded randomness and interactive parameters.
* **`canvas-design`:** Produce beautiful static visual art and posters exported cleanly as `.png` or `.pdf`.
* **`theme-factory`:** Instantly apply consistent visual themes (colors/fonts) across slides, docs, and HTML landing pages.
* **`brand-guidelines`:** Strictly enforce your company's official brand colors and typography on all AI-generated artifacts.
</details>

<details>
<summary><b>💻 Development & Engineering</b></summary>
<br>

* **`web-artifacts-builder`:** Build highly complex, multi-component React/Tailwind web artifacts featuring state management and routing (leveraging `shadcn/ui`).
* **`webapp-testing`:** Automatically test local web applications using Playwright. Verify frontend functionality, debug UI, and capture test screenshots.
* **`claude-api` (llm-api):** Build, debug, and optimize Claude API & Anthropic SDK integrations. Includes prompt caching and model migration strategies.
* **`mcp-builder`:** An authoritative guide for creating robust Model Context Protocol (MCP) servers in FastMCP (Python) or Node/TypeScript.
</details>

<details>
<summary><b>🛠️ Utilities & Meta-Skills</b></summary>
<br>

* **`skill-creator`:** **The crown jewel.** A meta-skill that allows the AI to create new skills from scratch, modify existing ones, run evaluations, benchmark performance, and optimize triggers.
* **`slack-gif-creator`:** Generate high-quality animated GIFs perfectly optimized for Slack constraints.
* **`internal-comms`:** Instantly generate properly formatted corporate communications, from status reports to incident post-mortems.
</details>

---

## 🏗️ Skill Architecture

How do these skills work so flawlessly? Every skill is built on a **Progressive Disclosure Architecture**, ensuring your LLM never drowns in context window bloat.

```text
skill-name/
├── SKILL.md                 # 📍 The core logic (< 500 lines)
│   ├── YAML frontmatter     # 🧠 Trigger definition (Metadata)
│   └── Markdown body        # ⚙️ Workflow instructions
└── Bundled Resources
    ├── scripts/             # 💻 Executable Python/JS tools
    ├── references/          # 📚 Deep-dive documentation
    └── assets/              # 🖼️ Templates, icons, fonts
```
* **Smart Triggering:** The YAML metadata tells the LLM exactly *when* to wake the skill up.
* **Lean Execution:** The `SKILL.md` acts as a lightweight orchestrator.
* **Deep Context on Demand:** `references/` and `scripts/` are only pulled into context when explicitly needed.

---

## 🛠️ Build Your Own Skills

Don't see what you need? Build it! The `skill-creator` tool walks the AI through a rigorous creation loop:

1. 🎙️ **Interview:** The AI extracts your intent, edge cases, and required formats.
2. 🧪 **Test Cases:** It generates realistic edge-case prompts.
3. 🏃 **Execution:** It runs the tests using the newly drafted skill.
4. 📈 **Iteration & Optimization:** You provide feedback, the AI refines the logic, and it runs a background loop to optimize the YAML triggers for maximum accuracy.

---

## 📊 Evaluation & Benchmarking

We don't guess if a skill works; we measure it. The framework includes an advanced evaluation suite:

- **A/B Testing:** Simultaneously runs test cases *with* the skill and *without* the skill (or against older versions).
- **Quantitative Assertions:** Grades outputs against verifiable metrics.
- **Efficiency Tracking:** Captures `total_tokens` and `duration_ms` for every single run.
- **Visual Eval Viewer:** Includes a built-in HTML viewer (`generate_review.py`) to visually compare outputs and grade iterations visually.

---

## 🤝 Contributing

We welcome contributions to make LLMs even more capable!

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingSkill`)
3. Commit your changes (`git commit -m 'Add some AmazingSkill'`)
4. Push to the branch (`git push origin feature/AmazingSkill`)
5. Open a Pull Request

---

<div align="center">
  <i>Built for the future of agentic coding and AI-assisted workflows.</i><br>
  <b>Happy Building! 🚀</b>
</div>
