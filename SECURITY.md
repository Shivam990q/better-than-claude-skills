# Security Policy

## 🔒 Reporting a Vulnerability

If you discover a security vulnerability within any skill, **please do NOT open a public issue.**

Instead, report it responsibly:

1. **Email:** Send details to **shivam990q@gmail.com** with the subject line `[SECURITY] better-than-claude-skills`
2. **Include:**
   - A detailed description of the vulnerability
   - Steps to reproduce the issue
   - Potential impact and severity assessment
   - Affected skill(s) and file path(s)
   - Any suggested fix (optional but appreciated)
3. **Expected response time:** Acknowledgment within **48 hours**, fix within **7 days** for critical issues

## 🛡️ Responsible Disclosure Timeline

| Step | Timeline |
|------|----------|
| Report received | Acknowledgment within **48 hours** |
| Initial assessment | Within **3 business days** |
| Fix development | Within **7 days** for critical, **14 days** for medium |
| Public disclosure | After the fix is merged and released |
| Credit | Reporter acknowledged in CHANGELOG.md (unless they prefer anonymity) |

## 📍 Scope

This security policy covers:

- **Skill scripts** (`scripts/` directories) — any executable Python/JavaScript code
- **API integrations** — skills that interact with external services (e.g., `claude-api`, `mcp-builder`)
- **Credential handling** — any skill that processes tokens, keys, or secrets
- **File I/O operations** — skills that read/write to the file system (e.g., `docx`, `xlsx`, `pdf`)
- **Network requests** — any outbound HTTP/HTTPS calls made by scripts
- **Dependency vulnerabilities** — known CVEs in bundled or referenced libraries

## 🚫 Out of Scope

The following are **not** considered vulnerabilities in this project:

- Issues in the LLM itself (Claude, Gemini, GPT) — report those to the respective vendor
- Prompt injection attacks on the AI platform — this is an inherent LLM concern, not a skill-level issue
- Denial of service via large files — skills process user-provided files by design
- Social engineering or phishing — not applicable to a code repository

## ✅ Best Practices for Skill Authors

When creating or modifying skills:

### Credentials & Secrets
- ❌ **Never** hardcode API keys, tokens, or secrets in SKILL.md or scripts
- ❌ **Never** include credentials in example code or references
- ❌ **Never** commit `.env` files or configuration with real credentials
- ✅ **Always** use environment variables for sensitive configuration
- ✅ **Always** add credential files to `.gitignore`

### Input Validation
- ✅ **Always** validate and sanitize user inputs in scripts
- ✅ **Always** validate file paths to prevent directory traversal
- ✅ **Always** check file sizes before processing to prevent memory exhaustion
- ✅ **Always** use parameterized queries if interacting with any data store

### Network Security
- ✅ **Always** use HTTPS for external API calls
- ✅ **Always** document any external network calls a skill makes
- ✅ **Always** implement request timeouts to prevent hanging connections
- ✅ **Always** validate SSL certificates (don't disable verification)

### Code Execution
- ✅ **Always** review third-party scripts before including them
- ✅ **Always** pin dependency versions in requirements or package.json
- ✅ **Always** prefer well-maintained libraries with active security patches

## ⚠️ Known Considerations

| Area | Status | Mitigation |
|------|--------|------------|
| Skills execute user-provided code | ⚠️ By design | Users should review scripts before execution |
| External API calls | ⚠️ Some skills make network requests | Documented per skill in SKILL.md |
| File system access | ⚠️ Some skills read/write files | Scoped to user-specified directories |
| Third-party dependencies | ⚠️ Scripts may use pip/npm packages | Dependencies documented in each skill |
| AI-generated code execution | ⚠️ Output may contain executable code | Users should review before running |

## 📋 Supported Versions

| Version | Supported |
|---------|-----------|
| Latest (main branch) | ✅ Active security support |
| Previous releases | ⚠️ Best-effort only |
| Forks & modifications | ❌ Not covered by this policy |

## 🏆 Security Acknowledgments

We appreciate responsible disclosure. Security researchers who report valid vulnerabilities will be credited here (with permission):

| Reporter | Vulnerability | Date | Status |
|----------|--------------|------|--------|
| — | — | — | No reports yet |

---

<div align="center">

Thank you for helping keep this project and its users safe! 🛡️

**If you find something, say something.** Your report makes the entire AI community safer.

</div>
