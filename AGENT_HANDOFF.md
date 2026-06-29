# Agent Handoff

Last updated: 2026-06-27 account/data deletion page checkpoint

Local project: `/Users/chanceneel/Projects/BillingBird-Store-Pages`
Current branch snapshot: `main`
Git status at handoff: dirty local page work, not committed or pushed

GitHub remotes:

- `origin`: `https://github.com/DeadStick-Digital/BillingBird-Store-Pages.git`

GitHub push readiness snapshot:

- `main` is pushed to `origin`.
- Latest pushed commit: `f14e405 docs: add store pages handoff`.
- Shell `gh` was re-authenticated with browser OAuth on 2026-06-15. Run `gh auth status` first if
  push fails on another machine.

## Start Here

1. Read `/Users/chanceneel/Projects/SuperAssistant/README.md`.
2. Run `git status -sb` and treat it as current truth.
3. Preserve unrelated local changes.
4. Continue from `Current Handoff` below.

## Handoff Rules

- Update this file before switching between Codex and Antigravity.
- Record active branch, summary, files touched, verification commands, known failures, and whether work is local-only, committed, pushed, or PR-backed.
- Do not store raw secrets, tokens, private keys, cookies, dashboard sessions, or credential-bearing URLs here.
- For GitHub pushes, remember that GitHub password auth is not valid for HTTPS Git operations. Use browser OAuth, SSH, or a PAT with repo/Contents write access.

## Model Routing

- Antigravity architect: `Gemini 3.1 Pro` for ambiguous, high-impact, security-sensitive, release, revenue, or cross-service decisions.
- Antigravity complex coder: `Gemini 3.5 Flash High` for multi-file implementation and hard build/debug loops.
- Antigravity normal coder: `Gemini 3.5 Flash Medium` for scoped features, tests, docs, and routine debugging.
- Antigravity runner: `Gemini 3.5 Flash Low` for inspection, formatting, command interpretation, and low-risk edits.
- Codex routing: use `GPT 5.5 High` as the default architect/lead for first-pass design, scope control, implementation planning, ordinary architecture decisions, and normal final review; escalate to `GPT 5.5 xhigh` only for high-risk architecture, persistence/schema migrations, security-sensitive decisions, App Store/TestFlight/release decisions, major cross-system refactors, production incidents, or final review before risky external actions; use `GPT 5.4-mini` for coding/build/test/debug loops once the plan is settled, escalating only if implementation becomes ambiguous or risky.

## Current Handoff

- Active task: Public account/data deletion support page for App Store / Google Play compliance.
- Last agent: Codex implemented the page locally and did not commit, push, publish, or change store
  dashboards.
- Summary of local changes:
  - Added `docs/account-deletion.html` with customer-facing account/data deletion instructions.
  - Linked the deletion page from `docs/index.html`, `docs/privacy.html`, and `docs/support.html`.
  - Updated `README.md` to list the deletion page.
  - Added `.gitignore` with `.DS_Store` and removed local `.DS_Store` working-tree noise.
- Verification on 2026-06-27:
  - Passed: `git diff --check`
  - Passed: local content search for `account-deletion.html`, `Account and Data Deletion`, and
    `BillingBird deletion request` across `docs/` and `README.md`.
- Public URL status:
  - The deletion page is local only until reviewed, committed, pushed, and deployed through GitHub
    Pages.
  - After publication, use the public HTTPS deletion URL for Google Play's account deletion URL.
- Next steps:
  - Review copy for exact store/privacy wording.
  - Commit and push after owner approval.
  - Verify the deployed privacy, support, and deletion pages are reachable over public HTTPS.
