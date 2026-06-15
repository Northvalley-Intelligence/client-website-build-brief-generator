# Mission

Generate the latest client website build prompt, client intake checklist, technical brief, website mission, content needs, and validation plan using assessment reports, client intake, demand data, and current MDE validation logic.

The product helps North Valley start client website builds with current evidence, clear missing information, and project-specific validation rather than copying old sites.

## Current Phase

Generation 0: MDE foundation and product definition.

## Current Phase Goal

Define the local mission, project identity, dependencies, risk register, initial task graph, and project-specific validation strategy before implementing the generator.

## What Matters Most

- Consume demand data and website assessment reports as evidence inputs.
- Detect stale, missing, weak, or contradictory assessment data before using it for current-site claims.
- Identify missing client details and content needs instead of inventing facts.
- Protect client privacy, internal MDE strategy, and confidential cross-client learning.
- Generate a client-safe launch pack with client questions, website mission, technical brief, content-needed checklist, validation strategy suggestion, and Codex build prompt.
- Keep future client website repos aligned to Northvalley repository, Next.js, Cloudflare Workers, and validation expectations.
- Record outbox events for central MDE without coupling client-safe artifacts to private central ledgers.

## Non-Goals For Generation 0

- Do not implement the generator yet.
- Do not create a real client website build prompt from private client data yet.
- Do not deploy anything.
- Do not copy central private MDE ledgers or cross-client lessons into generated client repos.

## Current Risks

- Generated prompts may rely on stale assessment evidence without requiring verification.
- Missing client details may be accidentally filled with invented claims.
- Generated client repos may expose private internal MDE strategy or cross-client information.
- Assessment reports may contain unsupported claims, such as missing pages or broken links without exact evidence.
- Generated build prompts may omit branch governance, Cloudflare deployment constraints, or required validation checks.

## Next

- Confirm upstream assessment and demand data source formats.
- Define the generator input schema for assessment data, client intake, and demand signals.
- Implement stale assessment, missing detail, confidentiality, and evidence traceability checks.
- Create controlled fixtures and generate the first sample brief only after the Generation 0 artifacts are accepted.
