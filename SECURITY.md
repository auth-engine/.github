# Security Policy

## Supported versions

AuthEngine is in early open-source release. Security fixes are applied to the **`main`** branch and included in the next tagged Docker image release.

| Version | Supported |
|---------|-----------|
| `main` (latest) | Yes |
| Older tags | Best effort — upgrade to latest |

Production deployments: [docs.authengine.org/deployment](https://docs.authengine.org/deployment/)

---

## Reporting a vulnerability

**Please do not report security vulnerabilities through public GitHub issues.**

If you discover a security issue:

1. **Email:** [qniranjan.dev@gmail.com](mailto:qniranjan.dev@gmail.com)  
   Subject line: `AuthEngine Security Report`
2. Include:
   - Description of the vulnerability
   - Steps to reproduce
   - Affected component (`auth-engine`, `auth-engine-dashboard`, or `auth-engine-infra`)
   - Impact assessment (if known)
   - Your GitHub username (optional, for credit)

You should receive an acknowledgement within **72 hours**. We will work with you on validation and a fix timeline.

When a fix is ready, we will:

- Publish a patched release (or document upgrade steps)
- Credit reporters who wish to be named (unless you prefer anonymity)

---

## Scope

In scope:

- Authentication bypass, session fixation, or privilege escalation
- OIDC/OAuth misconfiguration or token validation flaws
- SQL injection, IDOR, or multi-tenant isolation breaks
- Secrets exposure in repository or default configuration
- Infrastructure misconfigurations documented in `auth-engine-infra`

Out of scope (please use regular issues):

- Denial of service without a proven exploit chain
- Social engineering
- Issues in third-party services (AWS, MongoDB Atlas, Upstash, SendGrid, etc.)
- Vulnerabilities in dependencies already fixed upstream — report via Dependabot/PR instead

---

## Safe deployment reminders

Operators running AuthEngine in production should:

- Use strong `SECRET_KEY` and `JWT_SECRET_KEY` (32+ random bytes)
- Restrict EC2 security groups and RDS access
- Keep `/opt/authengine/.env` permissions at `600`
- Enable MFA for super-admin and platform operators
- Rotate credentials if they were ever committed or shared

See [Security overview](https://docs.authengine.org/security-overview/) for architecture-level guidance.

---

## Preferred languages

English is preferred for security reports.
