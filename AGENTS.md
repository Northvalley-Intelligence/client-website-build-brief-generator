# Agent Instructions

## Mission-Driven Engineering

At session start, read:

1. `MISSION.md`
2. `MISSION_UPDATES.md`
3. `.mde/state.json`
4. `.mde/validation-strategy.json`
5. `.mde/failing-bdds.json`
6. Latest `.mde/validation-runs/` records
7. Latest `.mde/generations/` records
8. `.mde/generation-summary.md`
9. `.mde/findings.json`
10. `.mde/validator-effectiveness.json`
11. `deploy/release-checks.json` when deployment is involved

Define or follow the project-specific Validation Strategy, generate Functional Validation scenarios including BDDs where useful, classify findings Critical/High/Medium/Low, implement until required Critical and High validations pass or are explicitly accepted/deferred, run two independent Validation Gate passes for phase exit, and update MDE artifacts before completion.

Keep human, agent, and deploy artifacts separate. Human docs should remain concise. Structured traceability, validation, decisions, and planning data belongs in `.mde/`.

## Project Context

This repo is for a generator, not a client website. It should generate client-safe launch packs for future client website repos using assessment evidence, demand data, and client intake.

Required context packs:

- `client-website-build`
- `website-assessment-to-build`

Load `pdf-generation` only if this project adds PDF/report output.

Generation 0 must not implement the generator. It defines mission, dependencies, risks, task graph, validation strategy, and outbox behavior first.
