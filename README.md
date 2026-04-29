<div align="center">

# 🚀 Better Than Claude Skills
**The Ultimate Skill Arsenal for LLMs & AI Agents**

<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=200&section=header&text=Better%20Than%20Claude%20Skills&fontSize=50&animation=fadeIn" width="100%" />
</p>

**Supercharge your AI assistants with 16+ highly-optimized, production-ready skills.**

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
  - [Option 1: Drag & Drop (Recommended)](#option-1-drag--drop-recommended)
  - [Option 2: Build & Package from Source](#option-2-build--package-from-source)
- [🧰 The Skill Arsenal](#-the-skill-arsenal)
  - [📄 Document & Data Mastery](#-document--data-mastery)
  - [🎨 Design & Visual Arts](#-design--visual-arts)
  - [💻 Development & Engineering](#-development--engineering)
  - [🛠️ Utilities & Meta-Skills](#️-utilities--meta-skills)
- [🏗️ Progressive Disclosure Architecture](#️-progressive-disclosure-architecture)
- [🛠️ Build Your Own Skills (Skill-Creator)](#️-build-your-own-skills-skill-creator)
- [📊 Evaluation & Benchmarking](#-evaluation--benchmarking)
- [🤝 Contributing](#-contributing)
- [📜 License](#-license)

---

## ✨ Why Use This Repository?

Modern LLMs are incredibly smart, but they often lack the strict, domain-specific context needed to execute complex, multi-step workflows flawlessly. **Better Than Claude Skills** bridges that gap by providing a curated, expertly engineered collection of skills.

<div align="center">
  <img src="https://raw.githubusercontent.com/andreasbm/readme/master/assets/lines/rainbow.png" width="80%" />
</div>

- 🎯 **Pinpoint Accuracy:** Skills are designed with **"Progressive Disclosure,"** meaning your AI only gets the context it needs, *when* it needs it, avoiding context bloat and hallucination.
- ⚡ **Zero-Friction Setup:** Pre-packaged `.skill` files are ready for immediate drag-and-drop deployment into your favorite AI UI.
- 🛠️ **Autonomous Improvement:** Features a built-in `skill-creator` that allows your AI to autonomously write, benchmark, and optimize *new* skills for you.
- 🎨 **Production-Grade Outputs:** Generate visually stunning UI designs, beautiful generative art, and perfectly formatted corporate documents.

---

## 📦 Quick Start Installation

Getting started takes less than 60 seconds. You have two paths to power up your assistant:

### Option 1: Drag & Drop (No-Code, Recommended)
*The fastest way to enhance your AI interface.*

1. **Download the Repository:** Clone or download the ZIP of this repository.
2. **Locate the Skills:** Open the directory: `claude (skill-zip) to upload directly/`
3. **Select Your Skill:** Find the desired `.skill` file (e.g., `frontend-design.skill`, `docx.skill`).
4. **Deploy:** **Drag and drop** the file directly into your AI assistant interface! 🪄
5. **Activate:** Ask your AI to use the skill (e.g., "Use the frontend-design skill to create a landing page").

### Option 2: Build & Package from Source (For Developers)
*Perfect for developers looking to modify or inspect skills before deploying.*

```bash
# 1. Clone the repository
git clone https://github.com/yourusername/better-than-claude-skills.git
cd better-than-claude-skills

# 2. Navigate to the target skill directory
cd frontend-design/

# 3. Make your edits
# Edit SKILL.md, scripts/, or references/ to customize the skill

# 4. Use the built-in bundler to package your custom skill
python -m scripts.package_skill path/to/skill-folder

# 5. The new .skill file will be generated and ready for use!
```

---

## 🧰 The Skill Arsenal

We've categorized our **16+ highly optimized skills** to help you find exactly what you need. Each skill acts as a focused expert in its domain.

### 📄 Document & Data Mastery
Supercharge your AI's ability to read, write, and manipulate complex file formats.

* **`docx` (word-processing):** Ultimate control over `.docx` files. Create, read, and manipulate Word documents with tables of contents, tracked changes, and flawless formatting using low-level XML manipulation and JavaScript libraries.
* **`xlsx` (spreadsheet-processing):** Advanced spreadsheet manipulation. Read, fix, format, and generate `.xlsx`, `.xlsm`, `.csv`, or `.tsv` files. Includes mandatory formula recalculation workflows.
* **`pdf` (document-processing):** Comprehensive PDF operations using `pypdf`, `pdfplumber`, and `reportlab`. Extract text/tables, merge, split, watermark, encrypt, fill forms, and run OCR. Avoids common Unicode rendering issues.
* **`pptx` (presentation-processing):** Create, edit, and extract content from professional `.pptx` presentation slides. Includes design ideas, color palettes, and visual QA automation.
* **`doc-coauthoring`:** A structured, context-rich workflow for co-authoring technical documentation, proposals, and engineering specs. Guides users through Context Gathering, Refinement & Structure, and Reader Testing.

### 🎨 Design & Visual Arts
Elevate AI generation from generic "AI slop" to museum-quality aesthetics.

* **`frontend-design`:** Generate distinctive, production-grade frontend interfaces with high design quality. Prioritizes bold aesthetics, strong typography, and precise spatial composition.
* **`algorithmic-art`:** Create stunning generative art using `p5.js` with seeded randomness and interactive parameters. Workflow: (1) Philosophical manifesto creation, (2) Programmatic expression.
* **`canvas-design`:** Produce beautiful static visual art and posters exported cleanly as `.png` or `.pdf`. Enforces design philosophies like "Concrete Poetry" or "Chromatic Language".
* **`theme-factory`:** Instantly apply consistent visual themes (colors/fonts) across slides, docs, and HTML landing pages. Choose from 10 curated themes like "Ocean Depths" or "Midnight Galaxy".
* **`brand-guidelines`:** Strictly enforce official brand colors and typography (e.g., Anthropic's palette and Poppins/Lora fonts) on all AI-generated artifacts.

### 💻 Development & Engineering
Empower your AI to build complex applications and robust server architectures.

* **`web-artifacts-builder`:** Build highly complex, multi-component React/Vite/Tailwind web artifacts featuring state management and routing (leveraging `shadcn/ui`). Includes a mandatory bundling workflow.
* **`webapp-testing`:** Automatically test local web applications using Playwright. Verify frontend functionality, debug UI, and capture test screenshots. Implements a "Reconnaissance-Then-Action" pattern.
* **`claude-api` (llm-api):** Build, debug, and optimize Claude API & Anthropic SDK integrations. Includes prompt caching, adaptive thinking strategies, and strict API usage hierarchies.
* **`mcp-builder`:** An authoritative guide for creating robust Model Context Protocol (MCP) servers in FastMCP (Python) or Node/TypeScript. Follows a 4-phase lifecycle: Planning, Implementation, Review/Testing, and Evaluation.

### 🛠️ Utilities & Meta-Skills
Tools that help you communicate better and build *even more* skills.

* **`skill-creator`:** **The crown jewel.** A meta-skill that allows the AI to create new skills from scratch, modify existing ones, run evaluations, benchmark performance, and optimize triggers.
* **`slack-gif-creator`:** Generate high-quality animated GIFs perfectly optimized for Slack constraints (dimensions, FPS, colors). Includes physics simulations (bounce, shake, pulse).
* **`internal-comms`:** Instantly generate properly formatted corporate communications, from status reports (3Ps) to incident post-mortems and company newsletters.

---

## 🏗️ Progressive Disclosure Architecture

How do these skills work so flawlessly without overwhelming the AI's context window? 

Every skill is built on a **Progressive Disclosure Architecture**. This means the AI isn't forced to read 10,000 lines of documentation upfront. Instead, it reads what it needs, *when* it needs it.

```text
skill-name/
├── SKILL.md                 # 📍 The core logic (< 500 lines)
│   ├── YAML frontmatter     # 🧠 Trigger definition (Metadata)
│   └── Markdown body        # ⚙️ High-level workflow instructions
└── Bundled Resources        # 📦 Loaded strictly ON-DEMAND
    ├── scripts/             # 💻 Executable Python/JS tools
    ├── references/          # 📚 Deep-dive documentation
    └── assets/              # 🖼️ Templates, icons, fonts
```

### The Three Layers
1. **Metadata (Always Present):** The YAML frontmatter acts as a "pushy" trigger, ensuring the AI invokes the skill appropriately for complex tasks.
2. **Body Instructions (Loaded on Activation):** `SKILL.md` acts as a lightweight orchestrator, telling the AI *how* to approach the problem.
3. **Bundled Resources (Loaded on Demand):** `references/` and `scripts/` are only pulled into the context window when explicitly required by the workflow.

---

## 🛠️ Build Your Own Skills (Skill-Creator)

Don't see what you need? Build it! The `skill-creator` tool is a meta-skill that walks the AI through a rigorous creation loop to build new skills for you.

### The Skill Creation Loop
1. 🎙️ **Interview:** The AI extracts your intent, edge cases, and required formats.
2. 📝 **Draft:** It generates the `SKILL.md` and initial scripts.
3. 🧪 **Test Cases:** It generates realistic edge-case prompts.
4. 🏃 **Execution:** It runs the tests using the newly drafted skill.
5. 📊 **Evaluate (Qual/Quant):** The AI helps you evaluate the results, automatically generating quantitative baselines and visual comparisons.
6. 📈 **Iteration & Optimization:** You provide feedback, the AI refines the logic, and it runs a background loop to optimize the YAML triggers for maximum accuracy.

---

## 📊 Evaluation & Benchmarking

We don't guess if a skill works; we measure it. The framework includes an advanced evaluation suite accessible via the `skill-creator`:

- **A/B Testing:** Simultaneously runs test cases *with* the skill and *without* the skill (or against older versions).
- **Quantitative Assertions:** Grades outputs against verifiable, hard metrics (e.g., "Did it use the correct font?", "Is the formula valid?").
- **Efficiency Tracking:** Captures `total_tokens` and `duration_ms` for every single run to monitor cost and speed.
- **Visual Eval Viewer:** Includes a built-in HTML viewer (`eval-viewer/generate_review.py`) to visually compare outputs and grade iterations side-by-side.

---

## 🤝 Contributing

We welcome contributions to make LLMs even more capable!

1. **Fork the repository**
2. **Create your feature branch:** `git checkout -b feature/AmazingSkill`
3. **Commit your changes:** `git commit -m 'Add some AmazingSkill'`
4. **Push to the branch:** `git push origin feature/AmazingSkill`
5. **Open a Pull Request**

---

## 📜 License

This project is licensed under the terms specified in the `LICENSE.txt` file. Some skills may contain proprietary instructions. Please review individual skill licenses where applicable.

---

<div align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&height=100&section=footer" width="100%" />
  <br>
  <i>Built for the future of agentic coding and AI-assisted workflows.</i><br>
  <b>Happy Building! 🚀</b>
</div>
