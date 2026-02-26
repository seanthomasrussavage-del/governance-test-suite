# Governance Test Suite

Automated test harness to **prove that governance-first AI systems hold under pressure**.

This repository focuses on verification, not feature work.  
Its job is to answer one question clearly:

> _"Do the gates, routes, and drift protections behave the way we say they do?"_

---

## Purpose

This repo exists to:

- Validate **governance rules** implemented in orchestration layers (e.g. LLM Governance Gate).
- Confirm **routing behaviour** for multi-agent workflows (e.g. Multi-Agent Router with HITL).
- Detect and prevent **silent drift** in configurations, routing logic, or policy checks.
- Provide **repeatable, automated evidence** that the system does what the docs claim.

This is a **portfolio-facing** test harness:
- Cleanly separated from production code
- Safe to show publicly
- Free of internal mysticism, lore, or private pantheon language

---

## Scope

This test suite is designed to exercise four pillars:

1. **What is allowed**  
   - Governance rules, allowed/blocked actions, and policy enforcement.

2. **Who gets to do it**  
   - Routing decisions, agent selection, and human-in-the-loop (HITL) requirements.

3. **How changes are governed**  
   - Drift detection, amendment workflows, and append-only histories.

4. **Prove it holds under pressure**  
   - Stress tests, edge cases, and regression protection for all of the above.

---

## Repository Layout

Planned structure (subject to small refinements):

```text
governance-test-suite/
├─ src/
│  ├─ __init__.py
│  ├─ assertions.py      # Shared helper assertions
│  ├─ fixtures.py        # Shared fixtures & sample payloads
│  └─ suites/
│     ├─ routing_suite.py        # Tests for agent routing & HITL rules
│     ├─ governance_suite.py     # Tests for allow/deny, policy enforcement
│     └─ drift_suite.py          # Tests for drift detection & amendments
│
├─ tests/
│  ├─ __init__.py
│  ├─ test_routing_suite.py
│  ├─ test_governance_suite.py
│  └─ test_drift_suite.py
│
├─ docs/
│  └─ spec.md             # Human-readable description of what is being proven
│
├─ README.md
├─ requirements.txt       # Minimal dependencies for running the tests
└─ pyproject.toml (optional)  # If we decide to define a package
