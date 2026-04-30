# Skills Index — Quick Reference

> Complete reference for all 16+ skills in the repository.

<br>

## 📑 At a Glance

| # | Skill | Category | Complexity | One-Line Description |
|:-:|-------|:--------:|:----------:|----------------------|
| 1 | [`docx`](docx/) | 📄 Document | 🟡 Medium | Full XML-level Word document creation & editing |
| 2 | [`xlsx`](xlsx/) | 📄 Document | 🟡 Medium | Spreadsheet analysis, formatting & generation |
| 3 | [`pdf`](pdf/) | 📄 Document | 🟡 Medium | PDF merge, split, encrypt, watermark & form fill |
| 4 | [`pptx`](pptx/) | 📄 Document | 🟡 Medium | Professional presentation creation with visual QA |
| 5 | [`doc-coauthoring`](doc-coauthoring/) | 📄 Document | 🟢 Easy | 3-stage collaborative document writing |
| 6 | [`frontend-design`](frontend-design/) | 🎨 Design | 🔴 Advanced | Production-grade UI with bold aesthetics |
| 7 | [`algorithmic-art`](algorithmic-art/) | 🎨 Design | 🟡 Medium | Generative art with p5.js & seeded randomness |
| 8 | [`canvas-design`](canvas-design/) | 🎨 Design | 🟡 Medium | Museum-quality static visual art & posters |
| 9 | [`theme-factory`](theme-factory/) | 🎨 Design | 🟢 Easy | 10 curated themes + custom theme generation |
| 10 | [`brand-guidelines`](brand-guidelines/) | 🎨 Design | 🟢 Easy | Brand color & typography enforcement |
| 11 | [`web-artifacts-builder`](web-artifacts-builder/) | 💻 Dev | 🔴 Advanced | Multi-component React/Vite web applications |
| 12 | [`webapp-testing`](webapp-testing/) | 💻 Dev | 🟡 Medium | Automated Playwright testing with screenshots |
| 13 | [`claude-api`](claude-api/) | 💻 Dev | 🟡 Medium | Claude API & Anthropic SDK integration |
| 14 | [`mcp-builder`](mcp-builder/) | 💻 Dev | 🔴 Advanced | Model Context Protocol server development |
| 15 | [`skill-creator`](skill-creator/) | 🛠️ Meta | 🔴 Advanced | Create, test & benchmark new skills autonomously |
| 16 | [`slack-gif-creator`](slack-gif-creator/) | 🛠️ Utility | 🟡 Medium | Animated GIF generation for Slack |
| 17 | [`internal-comms`](internal-comms/) | 🛠️ Utility | 🟢 Easy | Corporate communications formatting |

<br>

---

## 📄 Document & Data Mastery

### `docx` — Word Processing

| Property | Value |
|----------|-------|
| **Directory** | [`docx/`](docx/) |
| **Category** | Document & Data |
| **Triggers** | `create a word document`, `generate docx`, `write a proposal` |
| **Key Libraries** | docx, mammoth, xml2js |
| **Output Formats** | `.docx` |

**What it does:** Creates and edits Word documents with full XML-level control. Handles tables of contents, tracked changes, headers/footers, complex nested tables, embedded images, and custom styles. Goes beyond simple text generation to produce properly structured, print-ready `.docx` files.

**When to use:** Any time you need a properly formatted Word document — proposals, reports, contracts, resumes, letters, or any document that needs to look professional in Microsoft Word.

<br>

### `xlsx` — Spreadsheet Processing

| Property | Value |
|----------|-------|
| **Directory** | [`xlsx/`](xlsx/) |
| **Category** | Document & Data |
| **Triggers** | `create spreadsheet`, `analyze excel`, `csv to xlsx` |
| **Key Libraries** | pandas, openpyxl |
| **Output Formats** | `.xlsx`, `.xlsm`, `.csv`, `.tsv` |

**What it does:** Reads, fixes, formats, and generates spreadsheets. Handles conditional formatting, pivot tables, multi-sheet operations, and chart generation. Includes a mandatory formula recalculation workflow to prevent stale data — a common LLM pitfall.

**When to use:** Data analysis, financial reports, dashboards, data transformation, or any time you need structured tabular output with formatting.

<br>

### `pdf` — Document Processing

| Property | Value |
|----------|-------|
| **Directory** | [`pdf/`](pdf/) |
| **Category** | Document & Data |
| **Triggers** | `merge PDFs`, `create PDF`, `encrypt PDF`, `fill PDF form` |
| **Key Libraries** | pypdf, pdfplumber, reportlab |
| **Output Formats** | `.pdf` |

**What it does:** Comprehensive PDF operations — extract text/tables, merge, split, watermark, encrypt/decrypt, fill forms, add page numbers. Handles OCR for scanned documents and properly manages Unicode rendering pitfalls (superscripts, subscripts).

**When to use:** Any PDF manipulation — merging documents, adding watermarks, extracting data from PDFs, filling forms, or creating new PDF reports from scratch.

<br>

### `pptx` — Presentation Processing

| Property | Value |
|----------|-------|
| **Directory** | [`pptx/`](pptx/) |
| **Category** | Document & Data |
| **Triggers** | `create presentation`, `make slides`, `pitch deck` |
| **Key Libraries** | python-pptx |
| **Output Formats** | `.pptx` |

**What it does:** Creates and edits professional PowerPoint presentations. Includes curated color palettes, font pairing guides, layout strategies, and automated visual quality assurance using subagent-driven inspection.

**When to use:** Investor pitch decks, conference talks, training materials, sales presentations, or any professional slide deck.

<br>

### `doc-coauthoring` — Collaborative Writing

| Property | Value |
|----------|-------|
| **Directory** | [`doc-coauthoring/`](doc-coauthoring/) |
| **Category** | Document & Data |
| **Triggers** | `help me write`, `coauthor`, `document review` |
| **Output Formats** | Any text-based format |

**What it does:** Structured 3-stage collaborative writing: (1) Context Gathering — understands your goals, audience, and constraints, (2) Refinement & Structure — builds and iterates on the document, (3) Reader Testing — uses a fresh AI perspective to catch blind spots.

**When to use:** Technical documentation, proposals, specs, blog posts, or any document that benefits from structured iteration and review.

<br>

---

## 🎨 Design & Visual Arts

### `frontend-design` — Production UI

| Property | Value |
|----------|-------|
| **Directory** | [`frontend-design/`](frontend-design/) |
| **Category** | Design |
| **Triggers** | `build a website`, `create a landing page`, `design UI` |
| **Output Formats** | HTML, CSS, JS |

**What it does:** Generates distinctive, production-grade frontend interfaces. Prioritizes bold aesthetics, strong typography, and precise spatial composition. Explicitly avoids generic, template-looking, or "AI-looking" designs.

**When to use:** Landing pages, dashboards, portfolios, product pages, admin panels, or any frontend UI that needs to look professional and unique.

<br>

### `algorithmic-art` — Generative Art

| Property | Value |
|----------|-------|
| **Directory** | [`algorithmic-art/`](algorithmic-art/) |
| **Category** | Design |
| **Triggers** | `generative art`, `creative coding`, `p5.js art` |
| **Key Libraries** | p5.js |
| **Output Formats** | HTML (interactive), PNG (static) |

**What it does:** Creates stunning generative art using p5.js with a two-phase workflow: first a philosophical manifesto defining the artistic concept, then programmatic visual expression. Uses seeded randomness for reproducible outputs.

**When to use:** Art installations, creative coding projects, unique visual content, or exploring the intersection of code and aesthetics.

<br>

### `canvas-design` — Static Visual Art

| Property | Value |
|----------|-------|
| **Directory** | [`canvas-design/`](canvas-design/) |
| **Category** | Design |
| **Triggers** | `design a poster`, `create artwork`, `visual composition` |
| **Output Formats** | PNG, PDF |

**What it does:** Produces museum-quality static visual art and posters. Enforces design philosophies including "Concrete Poetry," "Chromatic Language," and "Geometric Silence." Mandates expert-level craftsmanship in composition, typography, and color.

**When to use:** Posters, prints, social media art, album covers, book covers, or any high-quality static visual.

<br>

### `theme-factory` — Visual Theming

| Property | Value |
|----------|-------|
| **Directory** | [`theme-factory/`](theme-factory/) |
| **Category** | Design |
| **Triggers** | `apply theme`, `color scheme`, `visual style` |
| **Built-in Themes** | Ocean Depths, Midnight Galaxy, Desert Rose, + 7 more |

**What it does:** Provides 10 curated visual themes that can be applied consistently across presentations, documents, and HTML pages. Also supports custom theme generation on the fly.

**When to use:** When you need consistent visual styling across multiple outputs, or want to quickly apply a professional color/font scheme.

<br>

### `brand-guidelines` — Brand Enforcement

| Property | Value |
|----------|-------|
| **Directory** | [`brand-guidelines/`](brand-guidelines/) |
| **Category** | Design |
| **Triggers** | `brand colors`, `brand guidelines`, `corporate identity` |

**What it does:** Strictly enforces official brand colors and typography. Includes precise hex codes, font stacks, and auto-fallback for missing fonts across platforms. Example: Anthropic's `#d97757` orange with Poppins/Lora font pairing.

**When to use:** Any brand-sensitive output — marketing materials, presentations, websites, or documents that must adhere to brand standards.

<br>

---

## 💻 Development & Engineering

### `web-artifacts-builder` — Complex Web Apps

| Property | Value |
|----------|-------|
| **Directory** | [`web-artifacts-builder/`](web-artifacts-builder/) |
| **Category** | Development |
| **Triggers** | `build web app`, `react app`, `complex frontend` |
| **Key Libraries** | React, Vite, Tailwind, shadcn/ui |

**What it does:** Builds multi-component web applications with proper state management, routing, and component architecture. Includes mandatory standalone HTML bundling workflow for easy deployment.

**When to use:** Dashboards, admin panels, multi-page applications, or any frontend that goes beyond a simple single page.

<br>

### `webapp-testing` — Automated Testing

| Property | Value |
|----------|-------|
| **Directory** | [`webapp-testing/`](webapp-testing/) |
| **Category** | Development |
| **Triggers** | `test my website`, `playwright test`, `debug frontend` |
| **Key Libraries** | Playwright |

**What it does:** Tests local web applications using Playwright. Follows the "Reconnaissance-Then-Action" pattern — first explores the app, then systematically tests functionality. Manages the full server lifecycle (start → test → teardown).

**When to use:** After building a web app, to verify functionality, catch bugs, and capture screenshots for documentation.

<br>

### `claude-api` — LLM API Integration

| Property | Value |
|----------|-------|
| **Directory** | [`claude-api/`](claude-api/) |
| **Category** | Development |
| **Triggers** | `claude API`, `anthropic SDK`, `LLM integration` |
| **Key Libraries** | @anthropic-ai/sdk |

**What it does:** Builds, debugs, and optimizes Claude API and Anthropic SDK integrations. Covers prompt caching, adaptive thinking strategies, model migration guides (Sonnet → Opus), and strict SDK vs. raw HTTP request hierarchies.

**When to use:** Building AI-powered applications, chatbots, content generation pipelines, or any system that uses the Claude API.

<br>

### `mcp-builder` — MCP Server Development

| Property | Value |
|----------|-------|
| **Directory** | [`mcp-builder/`](mcp-builder/) |
| **Category** | Development |
| **Triggers** | `MCP server`, `model context protocol`, `build MCP` |
| **Key Libraries** | FastMCP (Python), @modelcontextprotocol/sdk (Node) |

**What it does:** Authoritative guide for building Model Context Protocol servers. Supports FastMCP (Python) and Node/TypeScript. Follows a four-phase lifecycle: Planning → Implementation → Review/Testing → Evaluation.

**When to use:** Building custom tool integrations for Claude or other MCP-compatible AI platforms.

<br>

---

## 🛠️ Utilities & Meta-Skills

### `skill-creator` — The Crown Jewel 👑

| Property | Value |
|----------|-------|
| **Directory** | [`skill-creator/`](skill-creator/) |
| **Category** | Meta-Skill |
| **Triggers** | `create a skill`, `new skill`, `build skill` |

**What it does:** The meta-skill that lets the AI create new skills from scratch. Handles generation, modification, evaluation, benchmarking, variance analysis, and YAML trigger optimization. Full generation → testing → refinement loop.

**When to use:** When you need a new skill that doesn't exist yet, or want to improve an existing one.

<br>

### `slack-gif-creator` — Animated GIFs

| Property | Value |
|----------|-------|
| **Directory** | [`slack-gif-creator/`](slack-gif-creator/) |
| **Category** | Utility |
| **Triggers** | `create GIF`, `slack emoji`, `animated image` |
| **Key Libraries** | PIL/Pillow |
| **Output Formats** | `.gif` |

**What it does:** Creates high-quality animated GIFs optimized for Slack constraints (128×128 emoji, 480×480 message formats). Supports easing functions, physics simulations (bounce, shake, pulse), and frame-by-frame control.

**When to use:** Custom Slack emojis, team reactions, animated badges, or fun animated content.

<br>

### `internal-comms` — Corporate Communications

| Property | Value |
|----------|-------|
| **Directory** | [`internal-comms/`](internal-comms/) |
| **Category** | Utility |
| **Triggers** | `write an update`, `internal communication`, `3P update` |

**What it does:** Generates properly formatted corporate communications — 3P updates (Progress/Plans/Problems), newsletters, FAQ responses, incident reports, leadership updates, and team announcements. Enforces enterprise tone and formatting standards.

**When to use:** Team updates, executive summaries, incident postmortems, company-wide announcements, or any formal internal communication.

<br>

---

<div align="center">

**Can't find what you need?** Use the [`skill-creator`](skill-creator/) to build it yourself, or [request a new skill](https://github.com/shivam990q/better-than-claude-skills/issues/new?template=feature_request.md).

⭐ [Star the repo](https://github.com/shivam990q/better-than-claude-skills) · 🍴 [Fork it](https://github.com/shivam990q/better-than-claude-skills/fork) · 📖 [Read the Architecture](ARCHITECTURE.md)

</div>
