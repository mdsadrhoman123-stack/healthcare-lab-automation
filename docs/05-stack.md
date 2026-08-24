# 05 · The stack

Each choice, and the reason for it.

---

| Component | Why this one |
| :--- | :--- |
| **n8n** | Self-hosted orchestration — PHI stays inside the practice's boundary |
| **PostgreSQL (encrypted)** | Encryption at rest, access logged per read and write |
| **Audit logging** | Actor identity recorded on every touch of patient data |
| **Secure API integrations** | Encryption in transit between every stage |

## What was deliberately not used

- **A hosted automation SaaS.** Client data would transit a third party, and the failure handling would be limited to what that vendor exposes.
- **A bespoke application where automation was enough.** The cheapest system to maintain is the one with the least custom code in it.
- **Anything that could not be redeployed by someone else.** A system only one person can operate is a liability for the client.

---

[← 04 · Failure handling](04-failure-handling.md) · [06 · Results →](06-results.md)
