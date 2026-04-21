# EffectOS - Machine-Enforced Governance (MEG)

Deterministic governance for computational effects.
Runtime can propose, but only MEG can authorize and execute.

![Build](https://img.shields.io/badge/build-docs--ready-brightgreen)
![Model](https://img.shields.io/badge/model-MEG-blue)
![Policy](https://img.shields.io/badge/policy-deny--by--default-orange)

## What is EffectOS?

EffectOS is a governance-first compute model for high-assurance systems.
It removes execution authority from mutable runtime environments and applies deterministic policy checks before any state-changing operation.

This approach improves safety, auditability, and operational control for AI agents and critical automation.

## Project Purpose

Modern systems often trust runtime with both decision-making and execution.
EffectOS separates those concerns:

- Runtime handles reasoning and intent generation
- MEG validates intent against explicit policy
- MEG authorizes or denies effects deterministically
- Only authorized effects can materialize in the machine world

## MEG Agent SDK Flow Diagram

![MEG Agent SDK Flow Diagram](./assets/MEG%20Agent%20SDK%20Flow%20Diagram.svg)

## Product Demo Video

[![Watch Product Demo Video](./assets/video-preview.svg)](./assets/Rod%20Openclaw.mp4)

- GitHub README may not show an inline player for repo MP4 files.
- Embedded player page (full width): [Open Video Player](./docs/video-demo.html)

## Key Use Cases

- AI agent tool execution with strict effect controls
- Infrastructure automation with policy gates
- Compliance-heavy workflows with deterministic approvals
- Financial and operational actions requiring audit-first execution

Full details: `docs/use-cases.md`

## Documentation

- `docs/index.md` - Full documentation map
- `docs/purpose.md` - Mission, scope, and non-goals
- `docs/getting-started.md` - Quick onboarding steps
- `docs/policy-authoring-guide.md` - How to write safe deterministic policy
- `docs/threat-model.md` - Security risk model and controls
- `docs/operations-runbook.md` - Incident and operations procedures
- `docs/release-checklist.md` - Pre-release governance checklist
- `docs/integration-checklist.md` - Service/agent integration checklist
- `docs/testing-strategy.md` - What to test and why
- `docs/incident-response.md` - Incident handling playbook
- `docs/versioning-and-releases.md` - Versioning and release process
- `docs/adr/README.md` - Architecture decisions index

## Repository Standards

- `ARCHITECTURE.md` - MEG boundaries and system invariants
- `TESTING.md` - Required testing and release gate conditions
- `VERSIONING.md` - Versioning and release semantics
- `SECURITY.md` - Security and vulnerability reporting guidance
- `CONTRIBUTING.md` - Contribution workflow and quality rules
- `CHANGELOG.md` - Project change history

## Guiding Principle

If an effect is not authorized, it does not execute.
