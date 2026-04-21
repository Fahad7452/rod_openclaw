# Testing Strategy

## Goal

Validate that authorized effects execute and unauthorized effects fail deterministically.

## Test Layers

1. Unit tests for policy parsing and decision functions
2. Integration tests for runtime-to-MEG effect flow
3. Scenario tests for high-risk operations and failure cases

## Minimum Required Cases

- Allowed effect executes successfully
- Denied effect fails with clear reason
- Unknown effect type is denied by default
- Audit record is generated for every decision

## Regression Focus Areas

- Policy schema changes
- New effect type introduction
- Changes to authorization logic
- Changes to audit pipeline
