# Securitycode

Securitycode reviews code changes for security risks in Claude Code and Codex. It reads the original diff and relevant files, then returns a verdict, evidence, and fixes for confirmed findings. It can run on its own or as the `securitycode` role in [MyDevFactory](https://github.com/dimitriskl/mydevfactory).

## Install

Clone this repository, then copy the definition for your host into your target project's agent directory. Create the destination directory first if needed.

| Host | Definition to copy | Location in your project |
| --- | --- | --- |
| Claude Code | [`securitycode.md`](.claude/agents/securitycode.md) | `.claude/agents/securitycode.md` |
| Codex | [`securitycode.toml`](.codex/agents/securitycode.toml) | `.codex/agents/securitycode.toml` |

For personal installation, use the corresponding directory in your home folder. Start a session in the target project so the host can discover the agent. MyDevFactory's installer can install the pinned definitions for both hosts.

## Run a review

In your target project, ask your host to delegate to the agent and specify the diff or files:

```text
Delegate to securitycode. Review the diff from main to HEAD for security risks.
Return the verdict, file and line evidence, practical remediation, and review limits.
```

The agent issues `PASS`, `FAIL`, or `NOT RUN` for the assigned scope. A pass means it inspected the change and found no blocking security issue in that scope. The review uses local inspection and existing evidence. Choose a read-only sandbox where your host allows it if you need file writes to be technically prevented.

MyDevFactory sets the model and effort via its role configuration. For standalone use, the agent inherits your host's defaults.

[MIT license](LICENSE)
