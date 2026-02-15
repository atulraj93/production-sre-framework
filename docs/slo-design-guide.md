# SLO Design Guide: A Production-Centric Methodology

## Purpose

This guide defines a structured methodology for designing
Service Level Objectives (SLOs) that reflect user experience,
operational risk, and business continuity requirements.

The objective is to move beyond metric collection
and toward measurable reliability governance.

---

## The URO Model: User → Risk → Objective

This framework introduces the URO Model for SLO design:

1. User-Critical Interaction
2. Risk Quantification
3. Objective Definition
4. Error Budget Allocation
5. Operational Feedback Integration

---

## Step 1: Identify User-Critical Interactions

An SLO must represent a completed user action,
not an infrastructure measurement.

Examples:
- Successful trade submission
- Payment authorization completion
- Order confirmation
- Account authentication

Avoid:
- CPU usage
- Memory utilization
- Pod restart count

These are operational metrics, not reliability indicators.

---

## Step 2: Quantify Risk

Every SLO must explicitly define:

- Business impact of failure
- Acceptable degradation window
- Financial or reputational exposure
- Regulatory implications (if applicable)

This converts reliability into a risk management control.

---

## Step 3: Define the Objective

The objective must be:

- Statistically measurable
- Based on rolling windows
- Clearly owned by a team
- Actionable when breached

Example:

99.95% of successful transaction confirmations
within 250ms over a 30-day rolling window.

---

## Step 4: Error Budget Strategy

Error budgets should inform:

- Release freeze decisions
- Change velocity
- Incident severity classification
- Engineering prioritization

An SLO without policy enforcement is noise.

---

## Step 5: Operational Feedback Integration

SLO performance must influence:

- Deployment approval workflows
- Capacity planning
- Architectural refactoring
- Alert tuning

Reliability objectives must shape engineering behavior.

---

## Example: Financial-Grade Transaction Platform

Context:
Latency-sensitive system processing regulated financial transactions.

User-Critical Action:
Successful trade confirmation.

SLO:
99.99% successful confirmations within 200ms
over a 30-day rolling window.

Governance Implications:
- Error budget exhaustion triggers release freeze
- Elevated incident severity
- Immediate capacity review
- Executive visibility

High-availability systems require structured
reliability governance beyond monitoring.

---

## Anti-Patterns

- Arbitrary 99.99% targets without historical analysis
- Infrastructure-based SLOs disconnected from users
- Excessive SLO proliferation
- Ignoring burn rate alerts
- Undefined ownership

---

## Conclusion

SLO design is not a dashboard exercise.
It is a systematic risk governance mechanism
connecting user experience, engineering execution,
and business continuity.

