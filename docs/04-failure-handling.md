# 04 · Failure handling

The part of the system that took the longest to build and gets written about the least.

---

| What goes wrong | How it is detected | What the system does | Who finds out |
| :--- | :--- | :--- | :--- |
| **Result is outside expected range** | Reference range check | Routed to the physician queue — never auto-communicated | Physician notified |
| **Reference range is not configured** | Missing configuration | Held for physician review rather than compared to a generic range | Alert on the unconfigured marker |
| **Ingestion receives a malformed result** | Validation at ingestion | Rejected before storage, nothing partially written | Alert with the reference |
| **Any read or write of patient data** | Access logging | Not a failure — recorded so it can be audited later | Auditable after the fact |
| **Delivery to the patient fails** | Provider response | Held and retried; the record shows undelivered | Alert, not a silent drop |
| **Anything unanticipated** | Error handling per stage | Halt before patient communication | Alert with the record reference |

## The three rules behind that table

**1 — Fail closed, not open.** When the system cannot establish that an action is safe, it holds. A held item is a visible problem. An item processed on a guess is an invisible one.

**2 — Nothing disappears.** Anything that cannot be completed is recorded where a human can find it later, not dropped from the run.

**3 — Silence is a fault.** An empty result where results were expected is treated as a possible failure of the source, not as an absence of work. This is the check most automations skip.

---

[← 03 · Architecture](03-architecture.md) · [05 · The stack →](05-stack.md)
