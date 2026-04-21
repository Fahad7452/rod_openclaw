# Operations Runbook

## Purpose

Provide operational procedures for monitoring and handling MEG-governed execution flows.

## Daily Checks

- Verify MEG decision service health
- Check deny-rate anomalies by effect type
- Confirm audit trail ingestion is current
- Review top denied reasons for policy drift

## Incident: Unexpected Deny Spike

1. Identify affected effect types
2. Compare policy version before/after spike
3. Validate input schema changes from runtime
4. Roll back unsafe policy release if needed
5. Document incident timeline and root cause

## Incident: Unauthorized Execution Suspicion

1. Confirm whether execution path bypassed MEG
2. Freeze high-risk effect categories if supported
3. Collect and preserve audit evidence
4. Review integration boundary and credentials
5. Apply remediation and verify with test scenarios

## Emergency Policy Change Process

- Open emergency change record
- Apply minimal-scope change
- Require second reviewer if possible
- Set expiry for temporary exceptions
- Schedule post-incident cleanup

## Post-Incident Review

- What failed and why
- What controls worked
- What policy/test coverage is missing
- Which docs/runbooks must be updated
