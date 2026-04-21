# Agent SDK

Deterministic execution enforcement for AI agents.

## Example

from effectos import MEGGuard

guard = MEGGuard(policy="domain.json")
guard.execute("file.write", path="/etc/passwd")
# → denied
