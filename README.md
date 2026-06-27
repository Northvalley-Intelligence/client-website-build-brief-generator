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

This is a client-site cleanup and launch-readiness discipline, not a redesign instruction. Generated prompts should preserve the approved design direction, SEO structure, URLs, metadata, schema, navigation, page layouts, analytics, and conversion paths unless a specific quality issue requires a change.

Search all visitor-facing code and content, including pages, components, navigation, forms, metadata, schema, articles, project pages, service pages, FAQs, empty states, error messages, and public API responses. Public pages must not expose internal process language, including:

- AI content
- approved attribution
- approved examples
- API key
- automatic delivery
- configured yet
- current site
- current-site
- customer journey
- demo content
- deployment
- developer notes
- doorway pages
- example customer quote
- explains why
- implementation notes
- implementation
- not configured
- page purpose
- placeholder
- placeholder examples
- production version
- quote fit
- sample article
- sample articles
- service-area language
- style demo
- style demos
- SEO notes
- content strategy notes
- staging
- template explanations
- this page
- this page should
- this section
- this article
- the website should
- these images support
- webhook

HTML attributes such as `placeholder="..."` are acceptable only when the visible text is natural customer guidance. Do not expose the word "placeholder" to visitors as content.

Rewrite internal copy into natural customer-facing business English.

Examples:

- Bad: "These images support the customer journey."
- Good: "Our shop."
- Bad: "The website should not promise services the company does not offer."
- Good: "We review each repair individually before providing a quote."
- Bad: "This page groups nearby service-area language."
- Good: "The company serves customers from the listed local communities and nearby areas."
- Bad: "Automatic delivery is not configured yet."
- Good: "We could not send the request from the website right now. Please call or email with your details."
- Bad: "Example customer quote..."
- Good: "Many customers bring small repairs, one-off fabrication projects, trailer components, gates, and specialty metal parts to the shop."

Use only verified client facts, client-approved content, supplied photos, approved copy, and factual general statements. Do not invent testimonials, review excerpts, customer names, customer stories, project stories, before/after claims, certifications, awards, review counts, years in business, guarantees, service capabilities, locations served, or staff biographies.

If a section needs client input, keep it off public pages until supplied and approved. Replace public placeholders with general factual statements, or remove the section from public navigation/runtime pages.

If testimonials or review excerpts are not approved, use a factual statement instead and link to the official review/profile page when available.

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

- Before Launch
- Content Notes
- Materials Context
- Page Purpose
- Shop Context
- Quote Fit Details
- Why These Images
- SEO Coverage
- Sample Article
- Style Demo

Only change headings that still sound like internal notes. Do not rename good customer-facing headings unnecessarily.

Before handoff, the generated client website prompt must require every public route to be reviewed:

1. Read visible copy as a customer.
2. Remove anything that sounds like an AI prompt, documentation, engineering notes, SEO notes, or internal planning.
3. Replace explanatory headings with natural customer headings.
4. Confirm no fake testimonials, fake examples, fake projects, fake customer quotes, or invented proof are present.
5. Confirm placeholder/sample pages are not public, not linked in navigation, or return 404.
6. Confirm service pages describe the actual service, not why the page exists.
7. Confirm images are real supplied or approved assets with factual captions.

Pay special attention to service pages, service-area pages, project/gallery pages, reputation sections, article/blog pages, empty states, contact pages, quote/contact forms, FAQ pages, and 404/not-found pages.

Do not publish fake projects, fake case studies, fake articles, fake social posts, or style-demo content. Use only supplied or approved assets. If supplied photos are repetitive, reorder for variety and remove weak duplicates rather than inventing new work.

Remove public sample articles and public demo pages before launch. Confirm deleted sample URLs return 404 or redirect appropriately. Confirm navigation, sitemap, article indexes, and related links do not point to removed sample content.

Public form notes, empty states, public API responses, and error messages must tell customers what to do next. They must not expose internal setup state such as "not configured", "automatic delivery", "webhook", "API key", "staging", "production version", "deployment", "missing environment variable", or "provider setup".

Preferred fallback language:

"We could not send the request from the website right now. Please call or email with your details."

Only mark an item as client-dependent when it truly requires client input. Acceptable client-dependent items usually include additional real project photos, approved testimonials or review excerpts with attribution and permission, missing verified business facts, and final legal/compliance wording when required by the client. Do not mark cleanup, placeholder removal, fake-content removal, AI/process wording, broken navigation, or public implementation notes as client-dependent. Fix those directly.

Generated client website repos must add or update automated tests that guard against public AI/process wording, sample content, fake testimonials, deleted sample pages, and public setup/configuration language. Forbidden phrases may appear only in tests, internal docs, or validation reports as negative assertions.

After cleanup, generated prompts must require the project's local validation commands, including lint, typecheck, unit tests, build, and browser/e2e tests where available.

Production validation must run against the deployed URL, not only local. Production validation should confirm:

- public pages render
- public pages do not expose AI/process/template wording
- deleted sample pages return 404 or redirect appropriately
- forms show customer-facing fallback language
- no fake testimonials, projects, articles, or sample content are visible
- navigation does not link to removed sample content
- key conversion paths still work

Do not call client website work complete after deploying from an uncommitted local working tree. Before handoff for a production-deployed client website, the generated prompt must require:

1. Pull or rebase from GitHub `main`.
2. Run local validation.
3. Deploy production.
4. Run production validation against the deployed URL.
5. Commit the validated changes.
6. Push to GitHub `main`.
7. Confirm local `main`, `origin/main`, and production evidence are aligned.

Do not create multiple dated copies of the same client report. Keep one stable report filename and put dates in a Report History section inside the report. Use GitHub history as the backup trail.

For each client review issue, the handoff report must include:

1. Details.
2. Status: Fixed, No longer relevant, or Not fixed.
3. Explanation with before and after page content.
4. Latest link where the current version is available.
5. Reporter or source.

The handoff report must also include:

- Remaining AI/process wording found: should be 0.
- Remaining public placeholder pages: should be 0.
- Remaining client-dependent items: only items that genuinely need client input.
- Local validation commands and results.
- Production URL and deploy version when deployment is involved.
- GitHub sync status.
- A summary table with counts by issue status.

Success criterion: no visitor-facing page, form, API response, article, project, testimonial area, navigation item, metadata field, schema field, or empty state should reveal AI assistance, template construction, implementation notes, SEO commentary, fake proof, sample content, or internal launch/setup state.

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
