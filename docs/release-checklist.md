# Release Checklist

Use this checklist before each release.

## Governance and Policy

- [ ] Policy changes are reviewed and approved
- [ ] New effect types are documented
- [ ] Deny-by-default behavior verified for unknown effects
- [ ] Temporary emergency exceptions reviewed and expired if possible

## Quality and Testing

- [ ] Allowed-path integration tests pass
- [ ] Denied-path integration tests pass
- [ ] Regression checks for high-risk effects pass
- [ ] Audit decision reason codes are present and consistent

## Security and Reliability

- [ ] Security-impacting changes reviewed
- [ ] No known MEG bypass path in release scope
- [ ] Logging and monitoring dashboards updated
- [ ] Incident runbook references are current

## Documentation

- [ ] `README.md` reflects current capabilities
- [ ] `docs/use-cases.md` updated for new workflows
- [ ] `docs/policy-authoring-guide.md` updated if policy schema changed
- [ ] Changelog/release notes drafted
