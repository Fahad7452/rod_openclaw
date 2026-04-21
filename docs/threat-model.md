# Threat Model

## Objective

Document how EffectOS reduces high-impact execution risks by externalizing authority to MEG.

## Assets to Protect

- Execution authority for computational effects
- Policy integrity and version history
- Canonical audit trail integrity
- High-risk targets (payments, infra changes, data mutation)

## Primary Threats

1. Runtime compromise attempts unauthorized execution
2. Policy tampering introduces unsafe allow conditions
3. Audit log manipulation hides effect history
4. Replay of previously valid effect requests
5. Misconfigured integrations bypass MEG path

## Controls (Design-Level)

- Runtime has no direct state-change authority
- Positive authorization is required before execution
- Deny-by-default policy posture
- Immutable or protected audit records
- Deterministic decisioning with explicit reason codes

## Residual Risks

- Incorrect policy intent encoded by humans
- Weak integration points in early adoption phases
- Operational mistakes during emergency overrides

## Review Cadence

- Review threat model every release
- Re-review after major architecture changes
- Re-review after security incidents or near-misses
