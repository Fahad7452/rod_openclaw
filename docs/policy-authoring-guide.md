# Policy Authoring Guide

## Goal

Define deterministic, reviewable policies that decide whether a computational effect may execute.

## Authoring Principles

- Deny by default
- Use explicit allow rules
- Keep rules narrow and testable
- Separate policy logic from runtime logic
- Prefer deterministic inputs over dynamic heuristics

## Policy Structure (Recommended)

1. Effect type (for example, `file.write`, `command.exec`, `api.mutate`)
2. Target constraints (resource, path, endpoint, account)
3. Context constraints (environment, time window, actor class)
4. Risk limits (rate, amount, blast radius)
5. Decision output (`allow` or `deny`) with reason code

## Example Rule Shape

```json
{
  "effect": "api.mutate",
  "target": "payments/refund",
  "environment": "production",
  "constraints": {
    "max_amount": 500,
    "approval_required": true
  },
  "decision": "allow_if_all_constraints_pass"
}
```

## Validation Checklist

- Rule has a clear business purpose
- Rule cannot be bypassed by runtime
- Inputs are complete and canonical
- Failure mode is safe (`deny`)
- Decision reasons are audit-friendly

## Common Mistakes

- Broad wildcard rules in production
- Using mutable runtime state as the main trust anchor
- Mixing authorization and side effects in one step
- Missing reason codes for deny decisions
