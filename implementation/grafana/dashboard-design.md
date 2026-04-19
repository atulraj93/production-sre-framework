# Grafana Dashboard Design (PSGF)

---

## Panels

### 1. Success Rate (Primary)
- Line chart
- Threshold at 99.9%

---

### 2. Error Budget Burn Rate
- Gauge + time series

---

### 3. Latency (P95)
- Histogram or line

---

### 4. Request Volume
- Traffic context

---

### 5. Error Rate
- Complementary signal

---

## Layout Principle

Top → User impact  
Middle → Reliability metrics  
Bottom → System metrics  

---

## PSGF Principle

Dashboards should reflect:
User → SLO → Risk → Action
