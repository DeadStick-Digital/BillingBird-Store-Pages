# Agent Handoff

Last updated: 2026-07-16 Google Play listing and DeadStick email checkpoint

Local project: `/Users/chanceneel/Projects/BillingBird-Store-Pages`
Current branch snapshot: `main`
Git status at handoff: dirty local listing and contact-address work, not committed or pushed

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

- Active task: Prepare BillingBird's Google Play listing/support package and normalize public
  customer contact to `contact@deadstick.net`.
- Last agent: Codex prepared the package locally and did not commit, push, publish, change a Play
  Console dashboard, or contact anyone externally.
- Summary of local changes:
  - Added `GOOGLE_PLAY_LISTING.md` with draft listing copy, verified public URLs, current asset
    requirements and inventory, app-content checklist, and publication gates.
  - Added local Google Play asset drafts under `store-assets/google-play/`: a 512 x 512 app icon
    derived from the Android source icon and a generated 1,024 x 500 BillingBird feature graphic.
  - Normalized the customer-facing email to `contact@deadstick.net` in `docs/privacy.html`,
    `docs/support.html`, and `docs/account-deletion.html`.
  - Made backup, cloud, and subscription wording conditional on the installed release so the
    public pages do not present Android Google Drive backup, Play Billing, or cloud features as
    shipped before the release artifact proves them.
  - Normalized the four HTML doctypes so the local HTML validator accepts every page.
  - Kept the listing limited to release-proven local-first invoice, receipt, PDF, report, and
    export workflows. Google Drive backup, BillingBird Cloud, online payments, and Play Billing
    are explicitly excluded from listing claims until proven by the Android release artifact.
- Verification on 2026-07-16:
  - Passed: all three public GitHub Pages URLs returned HTTPS 200 before local edits.
  - Passed: repository-wide search found no remaining legacy support-address references.
  - Passed: app name 11/30 characters, short description 73/80, full description 885/4,000,
    and release notes 153/500.
  - Passed: `npx --yes html-validate@latest docs/*.html` for all four HTML pages.
  - Passed: every local HTML link resolves and every customer email link uses
    `mailto:contact@deadstick.net`.
  - Passed: privacy, support, and account-deletion public URLs each returned HTTPS 200.
  - Passed: feature graphic is 1,024 x 500 JPEG without alpha (106 KB); app icon is 512 x 512
    32-bit PNG with alpha (274 KB). Both still need final visual and Play-validator review before
    upload.
  - Passed: `git diff --check`.
- Public URL status:
  - GitHub Pages is built from `main` and `/docs` at
    `https://deadstick-digital.github.io/BillingBird-Store-Pages/`.
  - Privacy, support, and account-deletion URLs are publicly reachable.
  - The `contact@deadstick.net` replacement is local-only until owner-approved commit/push and the
    subsequent GitHub Pages rebuild; recheck deployed page content before Play Console entry.
- Next steps:
  - Review and approve the listing copy and customer-facing email change.
  - Commit and push only after owner approval, then verify the deployed contact address and links.
  - Review the draft icon and feature graphic, and capture required phone/tablet screenshots from
    the verified Android release build.
  - Complete Play app-content answers from the exact release artifact before upload or submission.
