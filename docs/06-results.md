# 06 · Results

---

## Counted

| | |
| :--- | :--- |
| Workflow nodes | **42** |
| Delivery milestone | **Phase 0 validation** |
| Autonomous clinical decisions | **0** |

These are counts from the built system: nodes, stages, versions, gates, retries. They are verifiable from the workflow itself.

## What changed in the process

| | Before | After |
| :--- | :--- | :--- |
| **Result interpretation** | Manual, per result | Automated against the practice's own ranges |
| **Out-of-range results** | Spotted if someone looks | Routed to a physician queue automatically |
| **Access to patient data** | Not systematically recorded | Logged with actor identity |
| **Data at rest** | Wherever it landed | Encrypted store |
| **Go-live** | One release and hope | Phase 0 validation before clinical use |

## What is deliberately not claimed

No time-saved percentage, cost-reduction figure or throughput multiplier appears in this repository. Those numbers require a measured baseline and a measured after, over a stated period, on a stated definition. Where that measurement exists it will be published with its method. Where it does not, the number is not worth more than the process description above.

> An unsourced percentage in a portfolio is a claim the reader has to take on trust. A node count is a claim they can check.

---

[← 05 · The stack](05-stack.md) · [07 · Limitations →](07-limitations.md)
