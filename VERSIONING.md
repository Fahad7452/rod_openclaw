# Versioning

## Scheme

Use semantic-style versioning:
- MAJOR: breaking changes
- MINOR: backward-compatible features
- PATCH: backward-compatible fixes

## Release Requirements

Before tagging a release:
- complete `docs/release-checklist.md`
- update `CHANGELOG.md`
- verify testing requirements in `TESTING.md`

## Breaking Change Rule

Every breaking change must include:
- migration notes
- explicit changelog entry
- rollback guidance

## Tag Format

Recommended tag format: `vX.Y.Z`
