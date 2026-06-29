# Agent Instructions

## Source Of Truth

Before operational work, read:

1. `/Users/chanceneel/Projects/SuperAssistant/README.md`
2. `AGENT_HANDOFF.md`

## Model Routing

- Codex routing: use `GPT 5.5 High` as the default architect/lead for first-pass design, scope control, implementation planning, ordinary architecture decisions, and normal final review; escalate to `GPT 5.5 xhigh` only for high-risk architecture, persistence/schema migrations, security-sensitive decisions, App Store/TestFlight/release decisions, major cross-system refactors, production incidents, or final review before risky external actions; use `GPT 5.4-mini` for coding/build/test/debug loops once the plan is settled, escalating only if implementation becomes ambiguous or risky.
- Antigravity routing follows the SuperAssistant README: `Gemini 3.1 Pro` for architect/release/security decisions, Flash High/Medium for implementation, and Flash Low for low-risk runner work.

## Operating Rules

- Inspect local status before edits and preserve unrelated user changes.
- Follow validation and handoff gates documented in `AGENT_HANDOFF.md`.
- Never print, commit, or store raw secrets, tokens, cookies, private keys, or credential-bearing URLs.
