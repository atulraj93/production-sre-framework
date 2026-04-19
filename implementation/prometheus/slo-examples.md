# SLO Definitions (PSGF - URO Model)

---

## Example: Payment System

### User
Payment completion

### Risk
Failed or delayed transactions impact revenue and trust

---

## Objective

99.9% successful payments within 300ms over 30 days

---

## Prometheus SLO Query

```promql
(
  sum(rate(app_requests_total{status="success"}[5m]))
/
  sum(rate(app_requests_total[5m]))
) >= 0.999

Error Budget
Allowed failure rate: 0.1%

Monthly error budget: 43.2 minutes of failure

PSGF Insight
SLO is derived from:
User → Risk → Objective (URO Model)
