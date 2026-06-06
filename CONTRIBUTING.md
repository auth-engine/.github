# Contributing to AuthEngine

Thank you for your interest in AuthEngine. This guide applies to all repositories in the [auth-engine](https://github.com/auth-engine) organization.

**Tagline:** One identity for every app and organisation.

---

## Repositories

| Repository | What to change here |
|------------|---------------------|
| [auth-engine](https://github.com/auth-engine/auth-engine) | FastAPI backend, IAM, OIDC, migrations |
| [auth-engine-dashboard](https://github.com/auth-engine/auth-engine-dashboard) | Next.js admin UI |
| [auth-engine-infra](https://github.com/auth-engine/auth-engine-infra) | Terraform, Docker Compose, documentation |
| [.github](https://github.com/auth-engine/.github) | Org profile, CONTRIBUTING, SECURITY |

**Documentation (canonical):** [docs.authengine.org](https://docs.authengine.org)

---

## Before you start

1. Read the [Quick Start](https://docs.authengine.org/quick-start/) and run the stack locally.
2. Search [existing issues](https://github.com/auth-engine/auth-engine/issues) — avoid duplicate work.
3. For large changes, open an issue first to discuss approach.
4. Look for issues labeled **`good first issue`** if you are new to the codebase.

---

## Local development

### Full stack (recommended)

```bash
git clone https://github.com/auth-engine/auth-engine-infra.git
cd auth-engine-infra/compose
cp env.local.example .env
# Set SECRET_KEY and JWT_SECRET_KEY (openssl rand -hex 32)

docker compose up -d --build
docker exec authengine-api auth-engine migrate
```

| Service | URL |
|---------|-----|
| API / Swagger | http://localhost:8000/docs |
| Dashboard | http://localhost:3000 |

Clone URLs in `compose/.env` default to the `auth-engine` org on GitHub.

### Backend only (`auth-engine`)

```bash
git clone https://github.com/auth-engine/auth-engine.git
cd auth-engine
uv sync
cp .env.example .env   # configure Postgres, Redis, MongoDB
auth-engine migrate
auth-engine run
```

Requires Python **3.12+**, [uv](https://docs.astral.sh/uv/), and running Postgres, Redis, and MongoDB (or use Compose from `auth-engine-infra`).

### Dashboard only (`auth-engine-dashboard`)

```bash
git clone https://github.com/auth-engine/auth-engine-dashboard.git
cd auth-engine-dashboard
cp .env.example .env.local
npm ci && npm run dev
```

Point `NEXT_PUBLIC_API_URL` at a running API (local or remote).

---

## Pull request workflow

1. **Fork** the repository and create a branch from `main`:
   - `feature/short-description`
   - `fix/short-description`
   - `docs/short-description`
2. **Keep PRs focused** — one logical change per PR when possible.
3. **Test locally** before opening the PR:
   - Backend: lint/typecheck via CI; run migrations if you changed models.
   - Dashboard: `npm run build` must pass.
   - Docs: verify links if you edited `auth-engine-infra/docs/`.
4. **Describe your PR:**
   - What changed and why
   - How you tested it
   - Related issue (`Fixes #123`)
5. Open the PR against **`main`**.

Maintainers will review when they can. Be patient — this is an early-stage open-source project.

---

## Code guidelines

- Match existing style in each repo (Ruff/mypy for Python, ESLint for TypeScript).
- Do not commit secrets (`.env`, API keys, passwords). Use `.env.example` for templates only.
- Add or update documentation in `auth-engine-infra/docs/` when behavior changes.
- Prefer small, readable diffs over large refactors unless discussed in an issue first.

---

## Reporting bugs and asking questions

| Type | Where |
|------|--------|
| Bug | [Bug report issue](https://github.com/auth-engine/auth-engine/issues/new?template=bug_report.yml) |
| Feature idea | [Feature request issue](https://github.com/auth-engine/auth-engine/issues/new?template=feature_request.yml) |
| Question | [Question issue](https://github.com/auth-engine/auth-engine/issues/new?template=question.yml) |
| Security vulnerability | See [SECURITY.md](SECURITY.md) or [docs — Security Policy](https://docs.authengine.org/security-policy/) — **do not** open a public issue |

---

## License

By contributing, you agree that your contributions will be licensed under the [MIT License](LICENSE) used across AuthEngine repositories.

---

## Contact

- **Website:** [authengine.org](https://authengine.org)
- **Docs:** [docs.authengine.org](https://docs.authengine.org)
- **Org:** [github.com/auth-engine](https://github.com/auth-engine)
