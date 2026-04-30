# Examples — Quick Start Guide

> Real-world usage examples to get you started with Better Than Claude Skills.

<br>

## 📑 Table of Contents

- [How Skills Work](#-how-skills-work)
- [Document & Data Skills](#-document--data-skills)
- [Design & Visual Skills](#-design--visual-skills)
- [Development Skills](#-development-skills)
- [Meta-Skills](#-meta-skills)
- [Combining Skills](#-combining-skills)

<br>

## 🧠 How Skills Work

1. **Install a skill** → Drag the `.skill` file into Claude's skill interface, or place the folder in your skill directory
2. **Trigger it** → Use natural language that matches the skill's triggers
3. **Let it work** → The AI follows the skill's structured workflow automatically

No configuration needed. No API keys. Just ask.

<br>

---

## 📄 Document & Data Skills

### `docx` — Word Processing

**Prompt:**
```
Create a professional project proposal document for a mobile app development 
project. Include title page, executive summary, scope, timeline table, budget 
breakdown, and team section. Use a modern blue color scheme.
```

**What the skill does:**
- Generates a `.docx` file with proper XML-level formatting
- Creates structured tables with borders, shading, and alignment
- Adds headers, footers, and page numbers
- Applies consistent typography throughout

<br>

### `xlsx` — Spreadsheet Processing

**Prompt:**
```
I have a CSV file with sales data. Create an Excel dashboard with:
- Monthly revenue summary with conditional formatting
- Top 10 products by sales volume
- Regional breakdown pivot table
- Charts for trends visualization
```

**What the skill does:**
- Reads and processes the CSV data using pandas
- Creates multiple formatted sheets with openpyxl
- Applies conditional formatting (color scales, data bars)
- Ensures all formulas are recalculated before saving

<br>

### `pdf` — Document Processing

**Prompt:**
```
Merge these 3 PDF files, add page numbers to the bottom of each page, 
add a watermark saying "CONFIDENTIAL" on every page, and encrypt 
the final PDF with a password.
```

**What the skill does:**
- Uses pypdf for merge operations
- Applies watermarks using reportlab canvas overlays
- Adds page numbers as footer annotations
- Encrypts with AES-256 encryption

<br>

### `pptx` — Presentation

**Prompt:**
```
Create a 12-slide investor pitch deck for an AI startup. Include:
- Title slide with company name and tagline
- Problem/Solution slides
- Market size and TAM analysis
- Product demo screenshots
- Team slide
- Financial projections with charts
- Ask slide (funding amount)
```

**What the skill does:**
- Generates `.pptx` with curated color palettes
- Uses professional font pairings
- Creates data-driven charts and graphs
- Applies consistent slide layouts and transitions

<br>

---

## 🎨 Design & Visual Skills

### `frontend-design` — Production UI

**Prompt:**
```
Build a modern SaaS pricing page with 3 tiers (Free, Pro, Enterprise). 
Include a dark theme, glassmorphism cards, toggle for monthly/annual billing, 
feature comparison table, and a FAQ accordion section.
```

**What the skill does:**
- Generates complete, production-ready HTML/CSS/JS
- Applies bold aesthetics — not generic or template-looking
- Implements interactive elements (toggles, accordions)
- Ensures responsive design across all breakpoints

<br>

### `algorithmic-art` — Generative Art

**Prompt:**
```
Create a generative art piece inspired by neural networks. 
Use flowing particle systems with connections between nearby nodes. 
Color palette: deep blues and electric purples on black.
```

**What the skill does:**
- Generates a p5.js sketch with seeded randomness
- Two-phase process: philosophical concept → visual code
- Creates interactive, explorable art pieces
- Reproducible outputs via seed parameter

<br>

### `canvas-design` — Static Visual Art

**Prompt:**
```
Design a minimalist poster for a tech conference called "Future Stack 2025". 
Style: Swiss design, geometric shapes, bold typography, limited color palette.
```

**What the skill does:**
- Creates museum-quality static visual art
- Enforces design philosophies and composition rules
- Outputs as `.png` or `.pdf` at print resolution
- Expert-level typography and spatial composition

<br>

---

## 💻 Development Skills

### `web-artifacts-builder` — Complex Web Apps

**Prompt:**
```
Build a project management dashboard with:
- Kanban board with drag-and-drop
- Task creation modal
- Team member assignment
- Due date calendar view
- Progress statistics sidebar
```

**What the skill does:**
- Scaffolds multi-component React/Vite application
- Implements state management and component communication
- Uses shadcn/ui for consistent design system
- Bundles into standalone HTML for easy deployment

<br>

### `webapp-testing` — Automated Testing

**Prompt:**
```
Test my local web app running on localhost:3000. Check:
- Login form validation
- Dashboard data loading
- Navigation between pages
- Responsive layout on mobile
- Take screenshots of each page state
```

**What the skill does:**
- Launches Playwright against your local server
- Follows "Reconnaissance-Then-Action" methodology
- Captures screenshots at each test step
- Reports pass/fail with detailed error messages
- Manages server lifecycle (start → test → teardown)

<br>

### `mcp-builder` — MCP Server Development

**Prompt:**
```
Build an MCP server that connects to a PostgreSQL database and exposes 
tools for: listing tables, running queries, and describing table schemas.
Use Python with FastMCP.
```

**What the skill does:**
- Follows 4-phase lifecycle: Planning → Implementation → Review → Evaluation
- Generates FastMCP server with proper tool registration
- Implements transport configuration and error handling
- Creates comprehensive test suite

<br>

---

## 🛠️ Meta-Skills

### `skill-creator` — Build New Skills

**Prompt:**
```
Create a new skill called "email-template" that generates professional 
HTML email templates for marketing campaigns. It should support 
different layouts: newsletter, product launch, event invitation.
```

**What the skill does:**
- Generates complete SKILL.md with YAML frontmatter
- Creates supporting scripts and reference files
- Runs automated evaluation against test prompts
- Benchmarks against no-skill baseline
- Iterates and refines based on results

<br>

---

## 🔗 Combining Skills

Skills can be used sequentially for complex workflows:

### Example: "Create and Test a Landing Page"

```
Step 1 (frontend-design): "Build a modern SaaS landing page with pricing, 
features, testimonials, and a signup form."

Step 2 (webapp-testing): "Test the landing page for responsive design, 
form validation, and cross-browser compatibility."

Step 3 (pdf): "Export the landing page design as a PDF for stakeholder review."
```

### Example: "Data Report Pipeline"

```
Step 1 (xlsx): "Analyze this sales data and create summary statistics."

Step 2 (pptx): "Create a presentation of the key findings from the analysis."

Step 3 (pdf): "Combine the Excel charts and PowerPoint slides into 
a single PDF report."
```

<br>

---

<div align="center">

**These are just starting points.** Every skill is designed to handle far more complex requests than these examples show.

The best way to learn? **Just try it.** Ask for what you need, and let the skill handle the details.

⭐ [Star the repo](https://github.com/shivam990q/better-than-claude-skills) if these skills save you time!

</div>
