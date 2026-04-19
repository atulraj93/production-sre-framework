# Error Budget & Burn Rate

---

## Error Rate

```promql
1 - (
  sum(rate(app_requests_total{status="success"}[5m]))
  /
  sum(rate(app_requests_total[5m]))
)

Burn Rate (Fast)

(
  1 - success_rate
) / (1 - 0.999)

Multi-Window Burn Rate (Recommended)

Short window:
avg_over_time(error_rate[5m])

Long window:
avg_over_time(error_rate[1h])


PSGF Governance Mapping
Burn rate informs:
Deployment control decisions
Incident severity
Reliability governance actions


