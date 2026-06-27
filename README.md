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

## Website Builder Instructions

Generated website build prompts must require every client website to feel like a polished, client-specific business website written by an experienced human copywriter who understands the client, the industry, and the customer's reason for visiting.

Visitors should never feel the site was AI-created, website-builder-generated, template-filled, or assembled from internal notes.

Public pages must not expose internal process language, including:

- AI content
- implementation notes
- developer notes
- SEO notes
- content strategy notes
- placeholder examples
- sample articles
- style demos
- template explanations
- current site
- this page
- this section
- this article
- this page should
- the website should
- customer journey
- quote fit
- page purpose
- explains why
- these images support
- service-area language
- doorway pages
- committed and deployed

Rewrite anything like that into natural customer-facing business English.

Examples:

- Bad: "These images support the customer journey."
- Good: "Our shop."
- Bad: "The website should not promise mobile service."
- Good: "We review each repair individually before providing a quote."
- Bad: "This page groups nearby service areas."
- Good: "Customers from Smyrna, Marietta, Atlanta, and nearby communities bring welding repair and fabrication projects to the shop."
- Bad: "Example customer quote..."
- Good: "Many customers bring small repairs, one-off fabrication projects, trailer components, gates, and specialty metal parts to the shop."

Use only verified facts, client-approved content, supplied photos, and approved claims. Do not invent testimonials, review snippets, customer names, ratings, review counts, certifications, staff biographies, project stories, before/after outcomes, case studies, awards, guarantees, services, locations, or credentials the client did not approve.

If a section needs client input, keep it off public pages until supplied and approved. Replace public placeholders with general factual statements, or remove the section from public navigation/runtime pages.

Use customer-facing headings such as:

- Our Shop
- Project Gallery
- What to Send
- Before Your Visit
- Materials
- Services
- Common Questions
- Directions
- Customer Feedback

Avoid internal headings such as:

- Shop Context
- Quote Fit Details
- Why These Images
- Page Purpose
- Content Notes
- SEO Coverage
- Sample Article
- Style Demo

Before handoff, the generated client website prompt must require every public route to be reviewed:

1. Read visible copy as a customer.
2. Remove anything that sounds like an AI prompt, documentation, engineering notes, SEO notes, or internal planning.
3. Replace explanatory headings with natural customer headings.
4. Confirm no fake testimonials, fake examples, fake projects, fake customer quotes, or invented proof are present.
5. Confirm placeholder/sample pages are not public, not linked in navigation, or return 404.
6. Confirm service pages describe the actual service, not why the page exists.
7. Confirm images are real supplied or approved assets with factual captions.

Generated client website repos must add a test or script that checks every public customer route for forbidden internal/process phrases. These phrases may appear only in tests, internal docs, or validation reports as negative assertions.

Do not call client website work complete after deploying from an uncommitted local working tree. Before handoff for a production-deployed client website, the generated prompt must require:

1. Pull or rebase from GitHub `main`.
2. Run local validation.
3. Deploy production.
4. Run production validation against the deployed URL.
5. Commit the validated changes.
6. Push to GitHub `main`.
7. Confirm local `main`, `origin/main`, and production evidence are aligned.

The handoff report must include:

- Remaining AI/process wording found: should be 0.
- Remaining public placeholder pages: should be 0.
- Remaining client-dependent items: only items that genuinely need client input.
- Local validation commands and results.
- Production URL and deploy version when deployment is involved.
- GitHub sync status.

## Current Status

This repo is in Generation 0. It has the mission, validation strategy, intake worksheet, risk register, and launch-package conventions, but it is not yet a full automated generator application.

The current intake worksheet template is:

`docs/client-intake-template.md`

The planned intake portal product spec is:

`docs/intake-portal-product-spec.md`

The draft structured form schema is:

`.mde/intake-portal-form-schema.json`

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
- Public Copy: generated website prompts must require human-written customer-facing copy, truth/proof review, public placeholder removal, forbidden-phrase route scanning, and GitHub/production sync evidence.

## Public Repo Boundary

This public repository is for the generator workflow and MDE structure. Do not commit:

- completed raw client intake forms
- private client contact details
- secrets, tokens, passwords, or API keys
- assessment reports that are not approved for publication
- generated client repos or client-owned assets

Use a private client repo for actual website implementation.
