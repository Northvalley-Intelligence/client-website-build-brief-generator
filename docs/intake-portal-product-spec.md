# Intake Portal Product Spec

## Mission

Create a low-friction client intake portal for website launch packages, hosted on a North Valley subdomain such as:

`https://intake.northvalleyintel.com`

The portal should make clients feel guided, not interrogated. It should collect only the facts needed to create a safe first website launch package, then offer optional sections for clients who want to provide more detail.

## Research Notes

Common website intake/questionnaire patterns repeat across agencies and form platforms:

- Content Snare groups intake around products/services, audience, competitors, USP, brand guidelines, budget, goals, content readiness, desired pages, desired features, inspiration sites, concerns, success criteria, and timeframe. It also highlights that long forms can stall projects and that clients benefit from being able to return later to finish. Source: <https://contentsnare.com/form-templates/web-design-questionnaire/>
- Jotform's website design questionnaire template includes contact details, business profile, business hours, mission/story, social links, assets/uploads, visual preferences, inspiration examples, requested pages, brand adjectives, and additional comments. Source: <https://www.jotform.com/form-templates/website-design-questionnaire>
- Nielsen Norman Group recommends progressive disclosure: show the most important options first and reveal specialized or advanced options only when requested. Source: <https://www.nngroup.com/articles/progressive-disclosure/>
- Nielsen Norman Group's form usability guidance starts with "keep it short," remove fields that can be derived or collected later, group related fields, and use a single-column layout. Source: <https://www.nngroup.com/articles/web-form-design/>
- Baymard's form research recommends explicitly marking required and optional fields, especially in longer forms, because ambiguity creates errors and hesitation. Source: <https://baymard.com/blog/required-optional-form-fields>

Decision: use a short staged form for the client-facing flow, with one optional expanded details section and one collapsed technical section.

## Product Shape

There are two experiences:

1. Client intake link:
   - Tokenized URL, for example `/i/resplendenttea?token=...`.
   - No account required.
   - Autosaves after each step.
   - Shows progress and estimated time.
   - Allows "I am not sure" or "North Valley can decide" for non-critical fields.

2. North Valley admin review:
   - Lists submitted intakes by status.
   - Lets Ferosh review, correct, and mark an intake as ready.
   - Shows missing launch blockers before launch-package generation.
   - Exports structured JSON for the launch package generator.

Do not collect secrets, passwords, API keys, Cloudflare tokens, registrar credentials, or Google credentials through the public form. Ask whether access exists and handle sensitive setup separately.

## Client-Facing Flow

### Step 1: Welcome

Purpose: reduce anxiety and set expectations.

Copy direction:

- "This should take about 5-8 minutes."
- "Answer what you know. You can skip optional details."
- "We use this to draft your website plan, not to publish anything automatically."
- "Technical details are optional."

### Step 2: Business Basics

Small mandatory set:

- Public business name.
- Primary contact name.
- Primary contact email.
- Current website or "I do not have one yet."
- Desired domain, if known.
- Public contact path preference: phone, email, form, booking link, or not sure.

Optional:

- Public phone.
- Business address visibility: show address, service-area only, not sure.
- Hours.
- Languages served.

Assessment defaults:

- If assessment exists, prefill current website, detected business name, detected phone/email, and detected address. Ask client to confirm or correct.
- If no assessment exists, leave blank and do not imply a current-site problem.

### Step 3: What You Offer

Small mandatory set:

- One-sentence business description.
- Top services/offers, minimum 1 and recommended max 5.
- Main customer types.
- Primary action visitors should take.

Optional:

- Services not offered.
- Seasonal services.
- Minimums, exclusions, booking rules.
- Pricing factors that can be explained publicly.

Assessment/demand defaults:

- Prefill service suggestions from assessment headings, existing pages, Google Business categories, or demand data when available.
- Let the client remove, rename, or reorder suggestions.
- Never invent service guarantees or credentials from inferred data.

### Step 4: Where You Work

Small mandatory set:

- Primary city/area.
- Additional service areas, if any.
- Whether location pages should be created now, later, or "North Valley can decide."

Optional:

- Areas not served.
- Travel fees or distance limits.
- Local proof, neighborhoods, landmarks, routes, or venue types.

Assessment/demand defaults:

- Prefill cities/areas from assessment report, current site, Google Business data, or demand data.
- If an assessment claims missing service-area pages, show it as a verification prompt, not as a fact.
- If local proof is weak, mark service-area pages as "needs content" instead of generating thin pages.

### Step 5: Proof And Assets

Small mandatory set:

- Do you have photos/logo ready? Yes / No / Need help.
- Upload up to 5 priority images:
  - logo
  - hero photo
  - service/product photo
  - team/owner photo
  - proof/event/project photo

Optional:

- Reviews/testimonials source.
- Google Business Profile URL.
- Licenses, certifications, awards, associations.
- Social profile links.
- Before/after photos, case studies, menus, PDFs, brochures, videos.

Rules:

- Uploads are optional, but the form should make clear that better assets improve the site.
- Every uploaded asset should capture permission status: approved for website use / not sure.
- Reviews/testimonials must require source and permission before appearing in generated public copy.

### Step 6: Style And Inspiration

Optional but visible, not mandatory.

- Choose 3-6 brand adjectives.
- Colors to use or avoid.
- Websites they like and why.
- Websites they dislike and why.
- Words or claims to avoid.

Default behavior:

- If skipped, North Valley chooses a restrained design direction from business type, audience, and available assets.

### Step 7: Technical Details

Collapsed by default. Label:

"Optional technical details if you know them"

Fields:

- Domain registrar.
- DNS host.
- Cloudflare status.
- Google Analytics status.
- Google Business Profile access.
- Existing Search Console access.
- Form/email provider.
- Booking, CRM, ecommerce, payment, newsletter, or chat tools.
- Known required integrations.

Rules:

- Do not ask for passwords or API keys.
- Do not require technical fields to submit.
- Mark unknown values as follow-up tasks.

### Step 8: Review And Submit

Show a friendly summary:

- Business name.
- Main offer.
- Primary area.
- Primary contact path.
- Assets uploaded.
- Optional sections completed.

Required confirmation:

- "I confirm North Valley can use this information to draft my website launch package."
- "I understand North Valley will confirm before publishing public claims."

After submission:

- Show next steps.
- Send confirmation email to client and North Valley.
- Store status as `submitted`.

## Minimum Mandatory Fields

These are the only fields required to submit the first version:

- `business.public_name`
- `contact.primary_name`
- `contact.primary_email`
- `website.current_website_status`
- `offer.one_sentence_description`
- `offer.primary_offerings`
- `audience.best_fit_customers`
- `location.primary_market`
- `conversion.primary_action`
- `approval.intake_use_consent`

Everything else is optional, prefilled from assessment/demand where possible, or becomes a missing-info item in the launch package.

## Intake Status Lifecycle

- `draft`: client has started but not submitted.
- `submitted`: client has submitted.
- `review_needed`: North Valley needs to review missing or contradictory details.
- `ready_for_launch_package`: intake is ready to generate a launch package.
- `launch_package_generated`: launch package has been created.
- `archived`: intake is no longer active.

## Privacy And Security

- Use tokenized client links.
- Store submissions privately.
- Do not commit completed intake data to the public generator repo.
- Do not collect credentials or secrets.
- Use signed upload URLs or equivalent controlled storage for images.
- Limit uploads to 5 priority images in the first client flow.
- Add malware/type/size checks before accepting files.
- Make deletion/correction possible from admin.

## Subdomain And Deployment

Recommended public URL:

`https://intake.northvalleyintel.com`

Recommended admin URL:

`https://intake.northvalleyintel.com/admin`

Implementation target:

- Next.js app.
- Supabase for private intake records and asset metadata.
- Supabase Storage or equivalent private object storage for uploads.
- Tokenized links generated by admin.
- Server-side validation.
- No public list of clients or submissions.

## Launch Package Mapping

The generator should turn submitted intake into:

- `docs/client-intake-summary.md`
- `docs/client-intake-needed.md`
- `docs/content-needed-from-client.md`
- `docs/website-build-brief.md`
- `docs/launch-validation-plan.md`
- `docs/deployment.md`
- `codex-build.prompt.md`

Missing optional fields should not block generation unless they affect:

- public identity
- public contact path
- service/offering clarity
- primary service area
- legal/safety/privacy claims
- deployment ownership

## MDE Validation Expectations

Critical:

- Client can submit the minimal intake without touching technical fields.
- Technical section is collapsed by default and optional.
- Required and optional fields are clearly marked.
- Assessment/demand defaults are editable and labeled as suggestions.
- Missing data becomes follow-up questions instead of invented launch-package claims.
- Uploaded assets do not publish automatically.
- No credentials or secrets are collected.

High:

- Client can save and resume.
- Admin can see missing launch blockers.
- Admin can mark intake ready for launch-package generation.
- Generated JSON maps deterministically to launch-package artifacts.
