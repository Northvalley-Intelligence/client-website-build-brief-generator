# Client Website Build Brief Generator

This project is an experiment in using Mission-Driven Engineering (MDE) to turn client website intake into a safer, more complete website launch package.

Instead of starting a client website by copying an older site or writing a loose prompt, this repo defines a repeatable pre-build workflow:

1. Collect client intake.
2. Check what evidence exists and what is missing.
3. Mark stale, weak, or unavailable assessment data.
4. Prevent invented claims about reviews, credentials, locations, guarantees, service proof, or current-site problems.
5. Generate a client-safe launch package for a new website repo.
6. Carry a project-specific validation strategy into that repo before implementation starts.

## Why MDE

MDE keeps the work anchored to mission outcomes rather than code output. For this project, that means the generator is judged by whether it helps a client website build start with:

- clear business mission and conversion goals
- known missing client details
- traceability from recommendations to intake, assessment evidence, demand data, or explicit assumptions
- privacy boundaries between internal strategy and client-safe artifacts
- a validation plan that matches the specific website being built

The repo uses MDE artifacts under `.mde/` to record project state, risks, draft BDDs, validation strategy, decisions, generation summaries, and validation runs.

## What This Repo Generates

For a client website, the intended output is a launch package that can be written directly into a new client repo:

- `MISSION.md`
- `MISSION_UPDATES.md`
- `.mde/project.json`
- `.mde/validation-strategy.json`
- `.mde/outbox/events.jsonl`
- `.mde/lessons-local.jsonl`
- `docs/client-intake-needed.md`
- `docs/content-needed-from-client.md`
- `docs/website-build-brief.md`
- `docs/launch-validation-plan.md`
- `docs/deployment.md`
- `codex-build.prompt.md`

That package should be client-safe. It should not include private central MDE ledgers, cross-client lessons, confidential internal strategy, raw credentials, or unpublished client notes.

## Current Status

This repo is in Generation 0. It has the mission, validation strategy, intake worksheet, risk register, and launch-package conventions, but it is not yet a full automated generator application.

The current intake worksheet template is:

`docs/client-intake-template.md`

Raw completed client intakes and client input files should stay local or private and are ignored by default.

## Validation Strategy

The project-specific Validation Gate is defined in:

`.mde/validation-strategy.json`

Key validation themes:

- Functional: generated launch packages must include all required artifacts.
- Mission Coverage: recommendations must trace to evidence, intake, or documented assumptions.
- Technical: generated prompts must preserve the Northvalley Next.js, TypeScript, Cloudflare, npm, Node 22, and validation baseline.
- Usability: launch packages must be usable in a new repo without private central files.
- UI Standards: generated website prompts must require real, useful contact and conversion paths.
- Privacy: client-safe artifacts must exclude confidential internal material.

## Public Repo Boundary

This public repository is for the generator workflow and MDE structure. Do not commit:

- completed raw client intake forms
- private client contact details
- secrets, tokens, passwords, or API keys
- assessment reports that are not approved for publication
- generated client repos or client-owned assets

Use a private client repo for actual website implementation.
