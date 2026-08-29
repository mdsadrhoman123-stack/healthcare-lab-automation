# 05 · The stack

Each choice, and the reason for it.

---

| Component | Why this one |
| :--- | :--- |
| **n8n** | Self-hosted orchestration — PHI stays inside the practice's boundary |
| **PostgreSQL (encrypted)** | Encryption at rest, access logged per read and write |
| **Audit logging** | Actor identity recorded on every touch of patient data |
| **Secure API integrations** | Encryption in transit between every stage |

## The decisions behind that table

### Why the physician queue cannot be taken out

**What it does.** Anything outside expected parameters routes to a person before it reaches a patient.

**What was turned down.** Releasing normal results automatically. That is where the volume is — and deciding that a result is normal is a clinical judgement, which is not a judgement this system is entitled to make on its own.

**What that costs.** A required bottleneck, permanently. Removing it would remove the reason the system is safe to use at all.

### Why it is self-hosted, with every read logged

**What it does.** Orchestration stays inside the practice boundary, storage is encrypted at rest, and the actor is recorded on every single touch of patient data.

**What was turned down.** A hosted orchestrator. Someone else's uptime problem instead of the practice's — and protected health information transits a vendor, and the audit trail becomes only as complete as what that vendor exposes.

**What that costs.** The practice owns the infrastructure, and every read costs a log write. Interpretation is also bounded by the reference ranges configured here, so this is not a general clinical tool.

### Why this one says Phase 0 out loud

**What it does.** It is described as validation, because it is not yet running against live patient records.

**What was turned down.** Describing it as production, like the others. It would read stronger in a portfolio — and it would be untrue, and in healthcare that is the exact claim a client would be right to check.

**What that costs.** It reads as the least finished project in the portfolio. That is a real cost, and it is the honest one.

## The rule that applies to all of them

**Nothing that only one person can operate.** A system that depends on the engineer who built it is a liability for the client, however well it runs on the day it is handed over. Every choice above had to survive that test before the technical merits mattered at all.

---

[← 04 · Failure handling](04-failure-handling.md) · [06 · Results →](06-results.md)
