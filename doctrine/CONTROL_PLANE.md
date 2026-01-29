# Control Plane Doctrine (Governed AI Systems)

A system is not “safe” because it is intelligent.
A system is safe because it is **governable**.

This repository treats governance as an engineering layer: a **control plane** that surrounds model capability with inspectability, constraints, and reversibility.

---

## 1. Definition

**Control Plane**: the layer that decides what the system is allowed to do, proves what it did, and enables rollback when wrong.

It is separate from the **agent stack** (tools, prompts, models, workflows) and exists to prevent “high-speed ungoverned execution.”

---

## 2. Core Control Primitives (Non-Negotiable)

A system is not governable unless it has:

1) **Decision Memory**
- decisions are stored as artifacts, not meetings
- each decision has an ID, owner, scope, and reversibility plan

2) **Stop Authority**
- the system must have explicit stop conditions
- humans must have “kill switch” power at defined gates

3) **Auditability**
- actions must be traceable to decisions
- changes must be explainable and reviewable

4) **Reversibility**
- every meaningful action must have a rollback path
- rollback must be testable, not theoretical

5) **Permissioned Execution**
- real-world actions require explicit authorization
- blast radius determines the strictness of gates

---

## 3. Boundary: Control Plane vs Agent Stack

### Agent Stack
- LLM calls
- prompts
- tools
- workflows / orchestration
- retrieval / memory modules

### Control Plane
- rules that constrain execution
- artifact schemas
- gates + approvals
- audit trails
- rollback semantics
- stop conditions
- ownership + accountability

> The agent stack generates motion.  
> The control plane governs motion.

---

## 4. Governance Loop

1) **Decisions** define intent and constraints  
2) Execution produces outcomes  
3) Outcomes sometimes produce **Incidents**  
4) Incidents update the control plane (new gates, policies, stop conditions)  
5) The system becomes harder to break over time

This is the difference between:
- “a fast agent”
and
- “an institution-grade decision system.”

---

## 5. What This Prevents

- invisible authority (“who approved this?”)
- untraceable changes (“why did it do that?”)
- non-reversible automation (“we can’t undo it”)
- silent drift (“it’s still working… but wrong”)
- governance theater (“we have policies” with no enforcement)

---

## 6. Repository Contract

This repo enforces a simple rule:

> If it’s not an artifact, it didn’t happen.

Artifacts are defined in `doctrine/schemas/`.
