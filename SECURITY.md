# Security Policy

## Reporting a Vulnerability

If you discover a security vulnerability within any skill, **please do NOT open a public issue.**

Instead, report it responsibly:

1. **Email:** Send details to the project maintainer directly
2. **Include:** A description of the vulnerability, steps to reproduce, and potential impact
3. **Expected response time:** Within 48 hours

## Scope

This security policy covers:

- **Skill scripts** (`scripts/` directories) — any executable code
- **API integrations** — skills that interact with external services (e.g., `claude-api`)
- **Credential handling** — any skill that processes tokens, keys, or secrets

## Best Practices for Skill Authors

When creating or modifying skills:

- ❌ **Never** hardcode API keys, tokens, or secrets in SKILL.md or scripts
- ❌ **Never** include credentials in example code or references
- ✅ **Always** use environment variables for sensitive configuration
- ✅ **Always** validate and sanitize user inputs in scripts
- ✅ **Always** use HTTPS for external API calls
- ✅ **Always** document any external network calls a skill makes

## Known Considerations

| Area | Status |
|------|--------|
| Skills execute user-provided code | ⚠️ By design — users should review scripts before execution |
| External API calls | ⚠️ Some skills make network requests — documented per skill |
| File system access | ⚠️ Some skills read/write files — documented per skill |

## Supported Versions

| Version | Supported |
|---------|-----------|
| Latest (main branch) | ✅ |
| Older commits | ❌ |

---

Thank you for helping keep this project and its users safe! 🛡️
