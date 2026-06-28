# Session Handoff

Last updated: 2026-06-27

## Repository Move Context

Ferosh is moving the code root out of iCloud Drive because the backup copy consumed most of the available iCloud storage.

Current session path:

`/Users/feroshjacob/Library/Mobile Documents/com~apple~CloudDocs/code/client-website-build-brief-generator`

Expected new path after move:

`/Users/feroshjacob/code/client-website-build-brief-generator`

If all sibling repos move together under `/Users/feroshjacob/code`, the central MDE relative path should remain `../mde`.

## Current Git State Before Handoff

- Branch: `main`
- Remote: `origin`
- Last pushed code/context commit before this handoff: `0f30e96140b2b7b00bbfc6274566bef87584740f`
- Working tree was clean before this handoff file was created.

After moving the folder, start the next Codex session from the new repo path and run:

```bash
git status --short --branch
git log --oneline -5
```

## MDE State

- Project: `client-website-build-brief-generator`
- This is the generator repo, not a client website repo.
- Current phase: Generation 0.
- Implementation status: not started.
- Latest generation before move: `GEN-006`.
- Latest validation run before move: `VAL-006`.
- Phase-exit validation pass count: `0/2`.

Important local context files:

- `AGENTS.md`
- `MISSION.md`
- `MISSION_UPDATES.md`
- `.mde/state.json`
- `.mde/validation-strategy.json`
- `.mde/generation-summary.md`
- `.mde/generations/GEN-006.json`
- `.mde/validation-runs/VAL-006.json`

## What Just Changed

Recent committed work:

- `bb7f9f8` refreshed this project from central `../mde`, adding outbox sync, repository governance, summary-first reporting, and Third-Person Validation Gate tracking.
- `5ec7cff` merged Lori public-copy guardrails into the existing builder instructions.
- `0f30e96` strengthened the website launch-readiness rules.

The current single source for generated website builder instructions is `README.md`, section `Website Builder Instructions`.

Do not recreate a separate public-copy guardrail doc. A prior duplicate doc was removed intentionally.

## Current Requirements Captured

Generated client website prompts must now require:

- polished, client-specific, customer-facing public copy
- no public AI/process/template/setup wording
- truth/proof review with no invented testimonials, projects, claims, staff bios, awards, guarantees, service capabilities, or locations
- review of pages, components, navigation, forms, metadata, schema, articles, project pages, service pages, FAQs, empty states, error messages, and public API responses
- removal or proper 404/redirect behavior for sample/demo pages
- customer-facing form fallback language instead of setup/configuration details
- local validation plus production URL validation for deployed client sites
- one stable client review report filename with dates in Report History
- client review handoff entries with details, status, before/after page content, latest link, and reporter/source

## Next Recommended Work

Continue Generation 0 by confirming upstream assessment and demand data source formats, then implement generator output contracts that include:

- launch-readiness cleanup rules
- production public-content validation
- stable handoff reporting
- stale assessment checks
- missing client detail checks
- privacy/confidentiality checks
- controlled fixtures before generating a first sample launch pack

Do not implement a real client website from this repo.

## Move/Restart Checklist

After the folder is moved:

1. Start Codex from the new project path.
2. Read `AGENTS.md`.
3. Read the MDE session-start artifacts listed above.
4. Confirm `../mde` exists from the new path.
5. Run `git status --short --branch`.
6. Verify the branch is clean and aligned with `origin/main`.
7. Continue from `GEN-006`, not from an MDE re-adoption flow.
