# Integration Checklist

Use this checklist when integrating EffectOS/MEG into a new service or agent.

## Boundary Setup

- [ ] Runtime cannot execute state-changing actions directly
- [ ] All effect requests are routed through MEG
- [ ] Effect types are explicitly defined and versioned

## Policy and Controls

- [ ] Initial policy covers all required effect types
- [ ] Unknown effect types are denied by default
- [ ] Production constraints are narrower than development constraints
- [ ] Approval requirements defined for high-risk effects

## Observability and Audit

- [ ] Every decision includes allow/deny reason code
- [ ] Audit records include request context and outcome
- [ ] Dashboard alerts configured for deny spikes and execution anomalies

## Testing

- [ ] Allowed effects execute successfully
- [ ] Disallowed effects fail deterministically
- [ ] Replay/duplicate request behavior tested
- [ ] Failure-path tests include degraded dependency scenarios

## Go-Live Signoff

- [ ] Security reviewer signoff
- [ ] Operations reviewer signoff
- [ ] Product owner signoff
