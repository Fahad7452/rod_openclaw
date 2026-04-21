# Testing

## Purpose

Testing must prove two outcomes:
- authorized effects execute correctly
- unauthorized effects fail deterministically

## Required Test Lanes

1. Policy unit tests  
   Validate rule parsing, matching, and decision determinism.

2. Integration tests  
   Validate runtime-to-MEG flow and deny-by-default behavior.

3. Scenario tests  
   Validate high-risk workflows and degraded dependency cases.

## Minimum Evidence for PRs

- At least one allowed-path verification
- At least one denied-path verification
- Decision reason code visible in logs/audit output

## Release Gate

A release should not proceed if:
- unknown effects are not denied
- audit records are missing for effect decisions
- MEG bypass is possible in integration path

See `docs/testing-strategy.md` for expanded guidance.
