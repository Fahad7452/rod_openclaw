# Architecture

## Core Model

EffectOS uses a two-plane model:
- Runtime plane: reasoning, planning, and proposing effects
- MEG plane: validation, authorization, and execution

Runtime never has direct authority to materialize state-changing effects.

## Invariants

1. No effect executes without explicit authorization.
2. Unknown effects are denied by default.
3. Authorization decisions are deterministic and explainable.
4. Every decision is recorded in the audit trail.

## Trust Boundaries

- Runtime is treated as mutable and potentially compromised.
- MEG is the execution authority boundary.
- Policy is the machine-enforced contract between intent and execution.

## High-Risk Effect Categories

- `command.exec`
- `file.write`
- `api.mutate`
- `value.transfer`

These require stricter constraints, review paths, and audit visibility.

## Design Consequences

- Policy quality directly affects safety.
- Integration paths must prevent MEG bypass.
- Operational runbooks are required for incident response and rollback.
