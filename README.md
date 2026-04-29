# Better Than Claude Skills 🚀

Welcome to **Better Than Claude Skills**! This repository is a comprehensive collection of optimized, high-performance "skills" designed to supercharge your AI assistants (such as Claude, Gemini, or custom LLM agents). These skills provide your AI with specialized abilities—ranging from generating algorithmic art and building complex web artifacts, to manipulating spreadsheets, Word documents, and PDFs, to even creating *new* skills autonomously.

<div align="center">
  <img width="1917" height="927" alt="image" src="https://github.com/user-attachments/assets/53b6ddae-5004-43b6-87df-a0169067cfa0" />
  <img width="1917" height="930" alt="image" src="https://github.com/user-attachments/assets/eceefd01-75fd-4924-8287-7a154e76dda0" />
  <img width="1919" height="922" alt="image" src="https://github.com/user-attachments/assets/676edd16-1549-4084-889e-e61cd96c2de0" />
  <img width="1919" height="926" alt="image" src="https://github.com/user-attachments/assets/ee6be33e-e9f8-45be-ad88-355767f6fc8e" />
</div>

---

## 📖 Table of Contents

1. [Overview](#-overview)
2. [Repository Structure](#-repository-structure)
3. [List of Available Skills](#-list-of-available-skills)
4. [Setup & Installation](#-setup--installation)
5. [Anatomy of a Skill](#-anatomy-of-a-skill)
6. [Creating & Improving Skills](#-creating--improving-skills)
7. [Testing & Benchmarking](#-testing--benchmarking)
8. [Best Practices](#-best-practices)

---

## 🌟 Overview

Skills are packaged sets of instructions, reference documents, and executable scripts that give LLMs the context and tools they need to perform complex, domain-specific tasks reliably. 

This repository not only houses a diverse set of powerful skills ready for immediate use but also includes the foundational **Skill Creator**—a meta-skill that allows the AI to autonomously draft, test, benchmark, and refine *new* skills.

---

## 📁 Repository Structure

The repository is organized into individual skill source directories and a dedicated folder for ready-to-deploy skill packages:

- **`/` (Root):** Contains directories for each skill's source code (e.g., `/docx`, `/pdf`, `/frontend-design`).
- **`claude (skill-zip) to upload directly/`**: Contains pre-packaged `.skill` files. These are ready to be uploaded directly into your AI assistant interface without any manual compilation.

---

## 🧰 List of Available Skills

Here is a detailed breakdown of the highly optimized skills available in this repository:

### 📄 Document & Data Processing
- **`docx` (word-processing)**: Create, read, edit, or manipulate Word documents (`.docx`). Handles tables of contents, tracked changes, formatting, and content extraction.
- **`xlsx` (spreadsheet-processing)**: Advanced spreadsheet manipulation. Open, read, edit, fix, format, and generate `.xlsx`, `.xlsm`, `.csv`, or `.tsv` files.
- **`pdf` (document-processing)**: Comprehensive PDF manipulation. Read, extract text/tables, merge, split, watermark, encrypt/decrypt, fill forms, and perform OCR.
- **`pptx` (presentation-processing)**: Create, edit, split, and extract content from `.pptx` presentation slides.
- **`doc-coauthoring`**: A structured workflow for co-authoring technical documentation, proposals, and specs efficiently.

### 🎨 Design & Visual Arts
- **`algorithmic-art`**: Create generative, algorithmic art using `p5.js` with seeded randomness and interactive parameter exploration.
- **`canvas-design`**: Create beautiful static visual art and posters in `.png` and `.pdf` formats.
- **`frontend-design`**: Create distinctive, production-grade frontend interfaces with high design quality (avoids generic AI aesthetics).
- **`theme-factory`**: Apply consistent themes (colors/fonts) across various artifacts (slides, docs, HTML landing pages) using 10 pre-set themes or on-the-fly generation.
- **`brand-guidelines`**: Strictly apply Anthropic's official brand colors and typography to artifacts.

### 💻 Development & Engineering
- **`web-artifacts-builder`**: Build complex, multi-component HTML/React/Tailwind artifacts with state management and routing (uses `shadcn/ui`).
- **`webapp-testing`**: Interact with and test local web applications using Playwright (verifying frontend functionality, debugging UI, capturing screenshots).
- **`claude-api` (llm-api)**: Build, debug, and optimize Claude API / Anthropic SDK apps, including prompt caching and model migrations.
- **`mcp-builder`**: Guide for creating high-quality Model Context Protocol (MCP) servers in Python (FastMCP) or Node/TypeScript.

### 🛠️ Utilities & Meta-Skills
- **`skill-creator`**: The ultimate meta-skill. Create new skills from scratch, modify existing ones, run evaluations, benchmark performance, and optimize trigger descriptions.
- **`slack-gif-creator`**: Create animated GIFs optimized specifically for Slack (includes constraints and validation tools).
- **`internal-comms`**: Generate properly formatted internal company communications (status reports, newsletters, FAQs, incident reports).

---

## 🚀 Setup & Installation

Using these skills is incredibly straightforward:

### Option 1: Direct Upload (Recommended)
1. Navigate to the `claude (skill-zip) to upload directly/` directory.
2. Locate the `.skill` file you wish to use (e.g., `frontend-design.skill`).
3. Drag and drop (or upload) the `.skill` file directly into your Claude/AI client interface that supports skill imports.

### Option 2: Build from Source
If you wish to modify a skill before using it:
1. Navigate to the specific skill directory (e.g., `cd frontend-design`).
2. Make your edits to the `SKILL.md` or any scripts/references.
3. Package the skill using the packaging script provided in the `skill-creator` tool:
   ```bash
   python -m scripts.package_skill path/to/skill-folder
   ```
4. Upload the resulting `.skill` file.

---

## 🏗️ Anatomy of a Skill

Every skill in this repository follows a strict, highly optimized structure designed for "Progressive Disclosure". This ensures the LLM doesn't get overwhelmed with context until it actually needs it.

```text
skill-name/
├── SKILL.md (required)
│   ├── YAML frontmatter (name, description required)
│   └── Markdown instructions (< 500 lines ideally)
└── Bundled Resources (optional)
    ├── scripts/    - Executable code for deterministic/repetitive tasks
    ├── references/ - Docs loaded into context as needed
    └── assets/     - Files used in output (templates, icons, fonts)
```

- **Metadata (YAML)**: Always in context. Determines *when* the skill triggers.
- **SKILL.md Body**: Loaded when the skill triggers. Contains the core logic and workflow.
- **Bundled Resources**: Only loaded when explicitly referenced by the LLM.

---

## 🤖 Creating & Improving Skills

Want to build your own skill? Use the **`skill-creator`**! 

The `skill-creator` skill guides the AI through a structured loop:
1. **Interview & Draft**: The AI interviews you about the intent, edge cases, and expected output, then drafts the `SKILL.md`.
2. **Test Cases**: The AI generates realistic test prompts based on the skill's purpose.
3. **Execution**: The AI runs the test cases using the drafted skill.
4. **Evaluation**: You review the outputs qualitatively, while the AI runs quantitative assertions.
5. **Iteration**: The AI refines the skill based on your feedback.
6. **Description Optimization**: The AI generates positive/negative trigger cases to optimize the YAML description, ensuring the skill triggers exactly when it should.

---

## 📊 Testing & Benchmarking

Quality is paramount. The `skill-creator` includes an advanced evaluation suite:
- **Baseline Comparisons**: The system runs test cases *with* the skill and *without* the skill (or against an older version) simultaneously.
- **Quantitative Assertions**: Skills are graded against verifiable metrics (e.g., "Did the output contain a valid JSON object?").
- **Timing & Tokens**: The system captures `total_tokens` and `duration_ms` for every run to monitor efficiency tradeoffs.
- **Eval Viewer**: A built-in HTML viewer (`generate_review.py`) allows you to visually compare outputs and leave structured feedback for the next iteration.

---

## 🧠 Best Practices for Skill Writing

If you are writing skills manually, follow the philosophy baked into these tools:

1. **Explain the "Why"**: Don't use heavy-handed `MUST`s. Modern LLMs have excellent theory of mind. Explain *why* a constraint exists, and the model will follow it more intelligently.
2. **Keep the Prompt Lean**: Remove instructions that aren't pulling their weight. If the LLM wastes time on a specific step, cut it or refine it.
3. **Bundle Repetitive Work**: If a skill requires the LLM to repeatedly write the same helper script (e.g., `create_docx.py`), write the script once, put it in the `scripts/` folder, and instruct the skill to execute it instead.
4. **Pushy Descriptions**: The YAML `description` is what triggers the skill. Make it slightly "pushy". Instead of *"A tool to build dashboards"*, write: *"Use this skill whenever the user mentions dashboards, data visualization, or internal metrics, even if they don't explicitly ask for a 'dashboard'."*

---

*Built for the future of agentic coding and AI-assisted workflows. Happy building!*
