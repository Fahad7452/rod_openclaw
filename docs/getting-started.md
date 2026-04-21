# Getting Started

## 1) Understand the Model

Before integrating, align on the two-plane architecture:
- Runtime: reasoning and proposal
- MEG: validation, authorization, execution

Read:
- `docs/concepts.md`
- `docs/architecture.md`

## 2) Define Effect Types

Identify the effect categories your system must govern, such as:
- `file.write`
- `command.exec`
- `api.mutate`
- `value.transfer`

## 3) Write Initial Policy

Start with explicit allow rules and deny by default.
Prefer narrow scope for:
- Targets
- Environments
- Time windows
- Operation methods

## 4) Integrate SDK Layer

Use the SDK to route runtime-proposed actions through MEG.
Runtime should not bypass MEG for state-changing operations.

## 5) Validate with Test Scenarios

Test both:
- Allowed effects that must succeed
- Disallowed effects that must fail deterministically

## 6) Enable Audit Workflows

Ensure every effect decision has a durable record for:
- Operational review
- Incident response
- Compliance verification
