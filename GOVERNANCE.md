# Governance Model

This document outlines the governance model for the **Better Than Claude Skills** project. As the project scales from a personal repository to a community-driven open-source initiative, transparent decision-making is critical.

## 🌟 The Vision

Our goal is to build the definitive open-source standard for AI cognitive architecture and prompt-engineering-as-code. We believe in:
- **Progressive Disclosure:** Context should be loaded dynamically, not dumped upfront.
- **Quality Over Quantity:** 10 highly-polished, verified skills are better than 100 broken ones.
- **Cross-LLM Portability:** While optimized for Claude, skills should be adaptable to any capable LLM.

## 👥 Roles and Responsibilities

### 1. The Core Maintainer(s) (BDFL Model)
Currently, the project operates under a Benevolent Dictator for Life (BDFL) model, led by the project creator (`@shivam990q`).

**Responsibilities:**
- Final say on architectural decisions, the direction of the project, and releases.
- Reviewing and merging major Pull Requests.
- Upholding the [Code of Conduct](CODE_OF_CONDUCT.md).
- Addressing security vulnerabilities.

### 2. Contributors
Anyone who submits a pull request, opens an issue, or helps improve documentation is a contributor.

**Responsibilities:**
- Adhering to the [Contributing Guidelines](CONTRIBUTING.md).
- Providing clear, reproducible bug reports.
- Assisting other community members in the issue tracker.

### 3. Reviewers / Skill Maintainers (Future Role)
As the repository grows, contributors who demonstrate deep understanding of the architecture and consistently provide high-quality PRs may be invited to become Reviewers for specific skill categories.

**Responsibilities:**
- Triage issues related to their domain.
- Reviewing PRs for style, security, and architectural alignment.
- Approving merges for minor updates within their domain.

## 🛠️ Decision Making Process

### Minor Changes (Bug fixes, typos, small tweaks)
- Can be implemented directly via Pull Request.
- Require review by at least one Maintainer/Reviewer.
- Usually merged within 48-72 hours.

### Major Changes (New skills, architectural shifts, tooling changes)
- Must start as an **Issue** or **Feature Request** before any code is written.
- The Core Maintainer(s) will review the proposal for alignment with the project's vision.
- Once approved ("Status: Accepted"), implementation can begin.
- Requires rigorous testing and strict adherence to the Progressive Disclosure architecture.

## 📝 Modifying Governance

This governance model is a living document. As the community grows, we may transition from a BDFL model to a more distributed consensus or steering-committee model. 

Any proposed changes to this document should be submitted as a Pull Request and will be evaluated based on what best serves the long-term health and sustainability of the project.
