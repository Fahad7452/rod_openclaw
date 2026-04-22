<h1 align="center">EffectOS — Machine-Enforced Governance (MEG)</h1>

<p align="center">
  <strong>Execution authority does not exist in runtime.</strong><br/>
  Runtime can reason. Runtime can request. Runtime cannot execute.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/build-docs--ready-brightgreen?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/model-MEG-blue?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/policy-deny--by--default-orange?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/status-patent--pending-red?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/discord-ready-7289DA?style=for-the-badge&logo=discord"/>
</p>

---

> **EffectOS and Machine-Enforced Governance (MEG) are patent-pending architectures defining a new model for governed compute.**

---

## What is EffectOS?

EffectOS is a **governance-first compute primitive** for high-assurance systems.

It removes execution authority from mutable runtime environments and applies **deterministic, cryptographically-validated policy checks** before any state-changing operation can occur.

Traditional systems trust runtime with both decision-making and execution. EffectOS separates those concerns permanently:

| Traditional Systems | EffectOS |
|---|---|
| Runtime decides what is allowed | Execution authority is externalized |
| Policies are mutable | Only positively authorized effects execute |
| Execution authority is inherited | Authorization is cryptographically validated |
| No audit guarantee | Deny-by-default with full audit trail |

---

## How It Works — Two-Gate Execution Model

```
┌─────────────────────────────────────────────────────┐
│              NON-AUTHORITATIVE RUNTIME               │
│         No Execution Authority · Proposals Only      │
│              Agent / API / CLI / User                │
└──────────────────────┬──────────────────────────────┘
                       │  Effect Proposal (P/A/G/E Envelope)
                       ▼
┌─────────────────────────────────────────────────────┐
│           GATE 1 — MEG GOVERNANCE LAYER              │
│  • Canonicalize effect                               │
│  • Validate via CHVE (Cryptographic Hash Validation) │
│  • Validate via THVE (Temporal Hash Validation)      │
│  • Write authorization proof to CAT                  │
└──────────────────────┬──────────────────────────────┘
                       │  CAT Proof
                       ▼
┌─────────────────────────────────────────────────────┐
│           GATE 2 — EXTERNAL EXECUTION                │
│  • Verify CAT proof                                  │
│  • Execute ONLY if authorized                        │
│  • No proof → No execution. Full stop.               │
└─────────────────────────────────────────────────────┘
```

**No proof → No execution.**

---

## Core Primitives

### Canonical Effects
Effects are strictly matched — no fuzzy authorization, no ambiguity. Every effect must be canonicalized before it can be evaluated by MEG.

### P/A/G/E Envelope Structure
Every effect proposal is wrapped in a structured envelope:
- **P** — Proposal
- **A** — Authorization context
- **G** — Governance metadata
- **E** — Effect payload

### Integrity Model — CHVE / THVE
- **CHVE** (Cryptographic Hash Validation Engine) — ensures effect integrity hasn't been tampered with
- **THVE** (Temporal Hash Validation Engine) — ensures authorization is valid within its time window

### CAT — Cryptographic Authorization Token
The proof artifact written by MEG after successful validation. External execution verifies the CAT before any action is taken.

---

## SDK Overview

> SDK enforces execution. MEG governs authority.

### Agent SDK
Agents operate inside the MEG boundary. They can reason and propose effects, but **cannot execute without a valid CAT authorization**. The Agent SDK handles envelope construction, CAT verification, and execution gating.

### API SDK
All API calls require validated effects. The API SDK enforces that every state-changing request passes through MEG before it can materialize. **No validated effect = request blocked.**

---

## Key Use Cases

- **AI Agent Execution** — Strict effect controls prevent agents from taking unauthorized actions
- **Infrastructure Automation** — Policy gates on every infrastructure change
- **Compliance Workflows** — Deterministic approvals with full audit evidence
- **Financial Operations** — Audit-first execution for high-risk transactions
- **Operational Technology (OT)** — Physical actions require explicit MEG authorization

---

## Demo

### Flow Diagram
![MEG Agent SDK Flow Diagram](./assets/MEG%20Agent%20SDK%20Flow%20Diagram.svg)

### Product Demo
<video controls width="100%" preload="metadata">
  <source src="https://raw.githubusercontent.com/Fahad7452/rod_openclaw/main/assets/rod-openclaw.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

🎬 Full video: [rod-openclaw.mp4](./assets/rod-openclaw.mp4)

---

## Trust and Execution Model

EffectOS creates enforceable governance boundaries that remain stable even if runtime behavior changes:

- Runtime **proposes** intents and effect candidates
- MEG **validates** each effect against explicit policy
- MEG **authorizes or denies** effects deterministically
- Only **positively authorized** effects are executed
- Denied effects are **blocked and retained** for audit visibility

---

## Security Model

### Design-Level Controls
- No direct runtime execution authority for high-impact effects
- Positive authorization required before execution
- Deny-by-default fallback for uncertain outcomes
- Deterministic decision outputs with explainable reason codes
- Protected audit trail model for post-incident review

### Threat Focus
EffectOS is designed to eliminate:
- Runtime compromise attempting unauthorized effect execution
- Policy tampering that broadens unsafe allow conditions
- Audit-trail manipulation hiding execution history
- Replay of previously valid effect requests
- Integration gaps that bypass MEG authorization paths

Full reference: [`SECURITY.md`](./SECURITY.md)

---

## Policy Authoring Principles

- Default to **deny** — add narrow allow rules only
- Use explicit target and context constraints
- Keep policy **deterministic and testable**
- Separate authorization from effect materialization
- Emit audit-friendly reason codes for allow and deny decisions

---

## Getting Started

1. Read [`docs/purpose.md`](./docs/purpose.md) — project purpose and boundary model
2. Review [`docs/getting-started.md`](./docs/getting-started.md) — integration requirements
3. Explore the [SDK Overview](./EffectOS_GitHub_Pack_v1/sdk/overview.md) — Agent SDK and API SDK
4. Study the [Execution Model](./EffectOS_GitHub_Pack_v1/primitive/execution-model.md) — two-gate model deep dive
5. Align testing with [`docs/testing-strategy.md`](./docs/testing-strategy.md)

---

## Documentation

| Document | Description |
|---|---|
| [`docs/index.md`](./docs/index.md) | Full documentation map |
| [`docs/purpose.md`](./docs/purpose.md) | Mission, scope, and non-goals |
| [`docs/getting-started.md`](./docs/getting-started.md) | Quick onboarding |
| [`docs/testing-strategy.md`](./docs/testing-strategy.md) | What to test and why |
| [`docs/versioning-and-releases.md`](./docs/versioning-and-releases.md) | Release governance |
| [`docs/adr/README.md`](./docs/adr/README.md) | Architecture decision records |
| [`ARCHITECTURE.md`](./ARCHITECTURE.md) | MEG boundaries and system invariants |
| [`SECURITY.md`](./SECURITY.md) | Security and vulnerability reporting |
| [`TESTING.md`](./TESTING.md) | Testing and release gate conditions |
| [`VERSIONING.md`](./VERSIONING.md) | Versioning semantics |

---

## Community

| | |
|---|---|
| [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md) | Community behavior expectations |
| [`MAINTAINERS.md`](./MAINTAINERS.md) | Maintainer roles and ownership |
| [`SUPPORT.md`](./SUPPORT.md) | Support and communication channels |

---

<p align="center">
  <strong>If an effect is not authorized, it does not execute.</strong>
</p>
