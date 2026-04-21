# ADR 0001: MEG Owns Execution Authority

## Status

Accepted

## Context

Runtime environments are mutable and compromise-prone.
If runtime holds execution authority, unauthorized state changes can occur even when intent logic is correct.

## Decision

Execution authority is externalized to MEG.
Runtime may propose effects but cannot execute state-changing operations directly.

## Consequences

### Positive
- Stronger control over high-risk effects
- Deterministic enforcement points
- Better auditability and incident analysis

### Negative
- Additional integration complexity
- Policy quality becomes a critical dependency

## Alternatives Considered

1. Keep execution in runtime with stronger guardrails
2. Hybrid model with partial MEG enforcement

## Effect on MEG Model

- Preserves strict runtime/MEG boundary
- Keeps deny-by-default enforceable
- Supports complete effect decision auditing
