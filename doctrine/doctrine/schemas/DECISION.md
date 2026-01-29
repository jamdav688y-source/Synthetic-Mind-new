# Decision Artifact Schema (Markdown)

A Decision is valid only if it includes every required field below.

> Purpose: Make decisions inspectable, owned, and reversible.

---

## Required Fields

### 1) Decision ID
- Format: `DEC-YYYY-MM-DD-<slug>`
- Example: `DEC-2026-01-29-local-first-execution`

### 2) Title
One line. Human readable.

### 3) Status
One of:
- Proposed
- Approved
- Rejected
- Reversed
- Deprecated

### 4) Owner
Single accountable human (name/role).

### 5) Decision
The actual choice made (clear, direct).

### 6) Context
Why this exists now (constraints, environment, pressure).

### 7) Assumptions
What must be true for this to work.

### 8) Alternatives Considered
At least 2 alternatives and why they were rejected.

### 9) Risk Tier + Blast Radius
- Tier 0 (no external impact) → Tier 3 (high stakes / irreversible)
- Describe what breaks if wrong.

### 10) Success Signals / Failure Signals
What measurable evidence says it’s working or failing.

### 11) Reversibility Plan
How to undo it safely (steps + triggers).

### 12) Stop Authority
Who can stop it, and under what conditions.

### 13) Audit Notes
How the system proves this decision governed execution.

---

## Optional Fields (Recommended)

- Related Decisions (IDs)
- Related Incidents (IDs)
- Review Date
- Attachments / Links

---

## Minimal Example (Template)

```md
# DEC-YYYY-MM-DD-slug — Title

**Status:** Proposed  
**Owner:** Name / Role  
**Risk Tier:** T1  
**Blast Radius:** ...

## Decision
...

## Context
...

## Assumptions
- ...

## Alternatives Considered
1) ...
2) ...

## Success Signals
- ...

## Failure Signals
- ...

## Reversibility Plan
- ...

## Stop Authority
- ...

## Audit Notes
- ...
