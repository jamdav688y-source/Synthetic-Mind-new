# Governance Model

## Purpose
Turn agent + automation work into decision-grade execution: bounded, reviewable, reversible.

## What Gets Gated (PR Required)
- Any change that increases autonomy (new triggers, schedules, background runs)
- Any integration that touches money, credentials, user data, or outbound messaging
- Any change that reduces observability (logs, alerts, audit trails)

## What Gets Logged (Issue Required)
- New risk vectors / threat models
- Any production anomaly, near-miss, or unexpected behavior
- Any policy exception (why it happened, who approved it, expiry)

## Escalation Triggers
Escalate immediately if any of the following occur:
- Unintended external action (messages sent, payments, posts, deletions)
- Credential exposure or suspicious access
- Repeat failure without a known root cause
- Drift: outputs change materially with no code/config change

## Stop Authority
Any operator may pause the system if an escalation trigger fires.
Pause first. Diagnose second. Resume only with:
- root cause hypothesis
- rollback plan
- monitoring signal that would prove “stable”

## Required Artifacts (per case)
- decision_packet.md (decision, owner, tradeoffs, reversibility)
- governance_scan.md (risks, controls, monitoring)
- incident_record.md (timeline, impact, fix, prevention)
- synthesis.md (what changed in the model going forward)