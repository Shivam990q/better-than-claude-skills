# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

<br>

## [Unreleased]

### 🔮 Planned
- Community-contributed skills marketplace
- Automated skill compatibility testing across LLM providers
- Visual skill builder (no-code skill creation)
- Skill chaining — compose multiple skills into pipelines
- Performance benchmarks dashboard

<br>

---

## [1.0.0] — 2025-04-30

### 🚀 Initial Release — The Skill Arsenal

16+ production-ready skills across 4 categories, built on the Progressive Disclosure Architecture.

<br>

#### 📄 Added — Document & Data Mastery

- **`docx`** — Word Processing
  - Full XML-level control over `.docx` files
  - Tables of contents, tracked changes, headers/footers
  - Flawless formatting using low-level XML manipulation and JavaScript libraries
  - Handles complex nested tables, images, and styles

- **`xlsx`** — Spreadsheet Processing
  - Read, fix, format, and generate `.xlsx`, `.xlsm`, `.csv`, `.tsv` files
  - Powered by `pandas` for data analysis and `openpyxl` for formatting
  - Mandatory formula recalculation workflows to prevent stale data
  - Conditional formatting, pivot table support, multi-sheet operations

- **`pdf`** — Document Processing
  - Comprehensive operations using `pypdf`, `pdfplumber`, and `reportlab`
  - Extract text/tables, merge, split, watermark, encrypt, fill forms
  - OCR integration for scanned documents
  - Unicode superscript/subscript rendering pitfall handling

- **`pptx`** — Presentation Processing
  - Create, edit, and extract content from professional `.pptx` slides
  - Curated color palettes and font pairing guides
  - Layout strategies and automated visual QA
  - Subagent-driven inspection for quality assurance

- **`doc-coauthoring`** — Collaborative Writing
  - Structured 3-stage workflow: Context Gathering → Refinement & Structure → Reader Testing
  - Fresh AI reader testing to catch blind spots
  - Supports technical docs, proposals, specs, and reports

<br>

#### 🎨 Added — Design & Visual Arts

- **`frontend-design`** — Production UI
  - Generates distinctive, production-grade frontend interfaces
  - Prioritizes bold aesthetics, strong typography, precise spatial composition
  - Never generic or "AI-looking" — enforces design craftsmanship

- **`algorithmic-art`** — Generative Art
  - Creates stunning generative art using `p5.js`
  - Seeded randomness for reproducible outputs
  - Two-phase workflow: Philosophical manifesto → Programmatic visual expression
  - Interactive parameters for real-time exploration

- **`canvas-design`** — Static Visual Art
  - Museum-quality visual art and posters as `.png` or `.pdf`
  - Enforces design philosophies: "Concrete Poetry," "Chromatic Language," "Geometric Silence"
  - Mandates expert-level craftsmanship and composition

- **`theme-factory`** — Visual Theming
  - 10 curated themes: Ocean Depths, Midnight Galaxy, Desert Rose, and more
  - Apply consistent visual themes across slides, docs, and HTML pages
  - Custom theme generation on the fly

- **`brand-guidelines`** — Brand Enforcement
  - Strictly enforces official brand colors and typography
  - Example: Anthropic's `#d97757` orange, Poppins/Lora fonts
  - Auto-fallback for missing fonts across platforms

<br>

#### 💻 Added — Development & Engineering

- **`web-artifacts-builder`** — Complex Web Apps
  - Build multi-component React/Vite/Tailwind web artifacts
  - State management and routing using `shadcn/ui`
  - Mandatory standalone HTML bundling workflow
  - Production-ready component architecture

- **`webapp-testing`** — Automated Testing
  - Test local web apps using Playwright
  - Verify frontend functionality, debug UI, capture screenshots
  - "Reconnaissance-Then-Action" pattern for systematic testing
  - Server lifecycle management (start, test, teardown)

- **`claude-api`** — LLM API Integration
  - Build, debug, and optimize Claude API & Anthropic SDK integrations
  - Prompt caching and adaptive thinking strategies
  - Model migration guides (e.g., Sonnet → Opus)
  - Strict SDK vs. raw HTTP request hierarchies

- **`mcp-builder`** — MCP Server Development
  - Authoritative guide for Model Context Protocol servers
  - Supports FastMCP (Python) and Node/TypeScript
  - Four-phase lifecycle: Planning → Implementation → Review/Testing → Evaluation
  - Transport configuration, tool registration, error handling patterns

<br>

#### 🛠️ Added — Utilities & Meta-Skills

- **`skill-creator`** — The Crown Jewel 👑
  - Meta-skill that lets the AI create new skills from scratch
  - Modify existing skills, run evaluations, benchmark performance
  - Variance analysis for consistency measurement
  - YAML trigger optimization for maximum accuracy
  - Full generation → testing → refinement loop

- **`slack-gif-creator`** — Animated GIFs
  - High-quality animated GIFs optimized for Slack constraints
  - 128×128 emoji and 480×480 message formats
  - Easing functions, physics simulations (bounce, shake, pulse)
  - PIL-based drawing with frame-by-frame control

- **`internal-comms`** — Corporate Communications
  - Properly formatted corporate communications
  - 3P updates (Progress/Plans/Problems), newsletters, FAQ responses
  - Incident reports, leadership updates, team announcements
  - Tone and formatting standards for enterprise environments

<br>

#### 🏗️ Added — Infrastructure

- **Progressive Disclosure Architecture**
  - 3-layer context management system (Metadata → Instructions → Resources)
  - Minimizes context window usage while maximizing precision
  - Near-zero hallucination through demand-loaded resources
  - Detailed in [ARCHITECTURE.md](ARCHITECTURE.md)

- **Drag-and-Drop Deployment**
  - Pre-packaged `.skill` files for instant deployment
  - No terminal, no setup, no code required
  - Compatible with claude.ai/customize/skills interface

- **Evaluation & Benchmarking Framework**
  - A/B testing: skill vs. no-skill comparison
  - Quantitative assertions for verifiable metrics
  - Efficiency tracking: `total_tokens` and `duration_ms` per run
  - Visual eval viewer (`generate_review.py`) for side-by-side grading

- **Repository Infrastructure**
  - MIT License
  - Contributing guidelines with quality checklist
  - Code of Conduct (Contributor Covenant v2.1)
  - Security policy with responsible disclosure
  - GitHub issue templates (bug report, feature request)
  - Pull request template with architecture compliance checks
