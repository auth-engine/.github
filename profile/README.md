# AuthEngine

**One identity for every app and organisation.**

AuthEngine is an open-source identity and access management (IAM) platform. It gives your applications a single place to handle sign-in, multi-tenant access control, OIDC federation, and audit — so you stop rebuilding login in every service.

People sign in once. Your APIs, dashboards, and partner apps all trust the same identity: who the user is, which organization they belong to, and what they are allowed to do.

AuthEngine is built for teams that run **more than one application** or **more than one customer organization** and need authentication, permissions, and policy to stay consistent across the stack.

AuthEngine provides a production-ready backend, an admin dashboard, and infrastructure tooling for deployment on **AWS EC2 with K3s, Rancher, and Helm** (in-cluster databases). Local development uses Docker Compose.

**Documentation:** [docs.authengine.org](https://docs.authengine.org) · [auth-engine-docs](https://github.com/auth-engine/auth-engine-docs)

| Host | Role |
|------|------|
| [api.authengine.org](https://api.authengine.org) | API + Swagger |
| [auth.authengine.org](https://auth.authengine.org) | OIDC / login UI |
| [app.authengine.org](https://app.authengine.org) | Admin dashboard |
| [docs.authengine.org](https://docs.authengine.org) | Documentation |

## Related repositories

| Repository | Role |
|------------|------|
| [auth-engine](https://github.com/auth-engine/auth-engine) | FastAPI backend — IAM, OIDC, introspection |
| [auth-engine-dashboard](https://github.com/auth-engine/auth-engine-dashboard) | Next.js admin dashboard |
| [auth-engine-data](https://github.com/auth-engine/auth-engine-data) | Roles, permissions & super-admin seeding |
| [auth-engine-docs](https://github.com/auth-engine/auth-engine-docs) | Platform documentation |
| [auth-engine-infra](https://github.com/auth-engine/auth-engine-infra) | Terraform & Docker Compose |
| [.github](https://github.com/auth-engine/.github) | Org profile, contributing & security policy |

---

## Contributing

We welcome issues and pull requests. Read **[Contributing](https://docs.authengine.org/contributing/)** or the org guide in **[CONTRIBUTING.md](https://github.com/auth-engine/.github/blob/main/CONTRIBUTING.md)**.
