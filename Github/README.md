# EffectOS - Machine-Enforced Governance (MEG)

Deterministic governance for computational effects.
Runtime can propose, but only MEG can authorize and execute.

![Build](https://img.shields.io/badge/build-docs--ready-brightgreen)
![Model](https://img.shields.io/badge/model-MEG-blue)
![Policy](https://img.shields.io/badge/policy-deny--by--default-orange)

## What is EffectOS?

EffectOS is a governance-first compute model for high-assurance systems.
It removes execution authority from mutable runtime environments and applies deterministic policy checks before any state-changing operation.

## Project Purpose

Modern systems often trust runtime with both decision-making and execution.
EffectOS separates those concerns:

- Runtime handles reasoning and intent generation
- MEG validates intent against explicit policy
- MEG authorizes or denies effects deterministically
- Only authorized effects can materialize in the machine world

## MEG Agent SDK Flow Diagram

![MEG Agent SDK Flow Diagram](MEG%20Agent%20SDK%20Flow%20Diagram.svg)

## Product Demo Video

Add your demo video file in this folder as:

- `rod-openclaw.mp4`

Embed the video in README using:

```html
<video src="https://raw.githubusercontent.com/Fahad7452/rod_openclaw/main/assets/rod-openclaw.mp4" controls width="100%"></video>
```

If inline playback is blocked, use direct link: [rod-openclaw.mp4](https://raw.githubusercontent.com/Fahad7452/rod_openclaw/main/assets/rod-openclaw.mp4)

## Key Use Cases

- AI agent tool execution with strict effect controls
- Infrastructure automation with policy gates
- Compliance-heavy workflows with deterministic approvals
- Financial and operational actions requiring audit-first execution

## Documentation

- `docs/architecture.md` - Two-plane model and control boundaries
- `docs/concepts.md` - Core concepts and terminology
- `docs/why-this-matters.md` - Motivation and problem framing
- `docs/faq.md` - Common questions and clarifications
- `docs/roadmap.md` - Current and future milestones

## Guiding Principle

If an effect is not authorized, it does not execute.
