# Changelog

## 1.1.0

- Add "Rounds and cost": report every blocking issue in round 1, fail only on blocking issues (hardening ideas are follow-ups), and in later rounds inspect only the previous findings and the fix range.
- Scale effort to the change: when the diff touches no trust boundary, confirm that from the diff and return `PASS` with the reason.
- Mark each finding `blocking` or `follow-up`.

## 1.0.0

- Add the defensive code security review agent for Claude Code and Codex.
