# SLI Metrics Definition

This document defines Prometheus-based Service Level Indicators (SLIs)
aligned with the PSGF framework.

---

## 1. Success Rate SLI (User-Centric)

Represents successful completion of user-critical actions.

### Metric

app_requests_total{status="success"}
app_requests_total{status="failure"}


### Query

```promql
sum(rate(app_requests_total{status="success"}[5m]))
/
sum(rate(app_requests_total[5m]))

## 2. Availability SLI (System-Level)

Represents system responsiveness.

### Query

sum(rate(http_requests_total{code!~"5.."}[5m]))
/
sum(rate(http_requests_total[5m]))


## 3. Latency SLI

P95 latency:

histogram_quantile(0.95,sum(rate(http_request_duration_seconds_bucket[5m])) by (le))


PSGF Note
Success Rate is the primary reliability indicator, as it reflects user outcome correctness.
