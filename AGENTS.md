AGENTS.md — Project Rules

1. Purpose

This project is a new landing page built from the existing Albuongusto website.

Albuongusto is the technical, structural and visual foundation.

The project must evolve incrementally.

Do not rewrite the project from scratch.

Do not introduce a new architecture unless explicitly requested.

Do not perform broad refactors unless required for the requested task.

2. Relationship with README.md

README.md describes the project's development workflow and general process.

AGENTS.md contains the mandatory rules the AI coding agent must follow.

Both files are complementary:

AGENTS.md = rules and constraints

README.md = development workflow and project guide

Do not duplicate or contradict the other file unnecessarily.

If a specific rule in AGENTS.md conflicts with a general workflow description in README.md, follow AGENTS.md.

3. Before Any Changes

Before modifying the project:

Read AGENTS.md.

Read README.md.

Inspect the project structure.

Identify the relevant HTML, CSS, JavaScript, assets and data.

Understand the existing implementation and dependencies.

Do not start editing before understanding the relevant part of the project.

4. Mandatory Development Method

Use this workflow:

AUDIT
→ RESEARCH
→ VERIFY
→ PLAN
→ MODIFY ONE LOGICAL PART
→ TEST
→ REVIEW
→ COMMIT
→ NEXT PART

Work incrementally.

If the user asks for one section, work on that section only unless another file must change for it to function correctly.

Do not make unrelated improvements automatically.

5. Preserve the Existing Implementation

Preserve whenever possible:

HTML structure

CSS architecture

class names

IDs

data-* attributes

JavaScript selectors

JavaScript behavior

animations

transitions

scroll effects

responsive behavior

accessibility attributes

existing interaction patterns

Do not rename classes, IDs or data attributes only for aesthetic reasons.

Before changing or removing an element, check whether CSS or JavaScript depends on it.

Do not replace working JavaScript or CSS architecture without a clear reason.

Do not introduce React, Vue, Tailwind, Bootstrap or another framework unless explicitly requested.

6. Research Before Content Changes

When replacing content with information about the new business or brand:

Do not invent facts.

Research first.

Prefer sources in this order:

official website

official social profiles

official tourism or government sources

official maps/business listings

current menus or catalogues

reputable review platforms

Verify important information such as:

name

address

phone

website

social profiles

services/products

menu

prices

opening information

history

location claims

architecture

landmarks

If something cannot be verified, do not present it as fact.

Use neutral wording or ask the user.

7. Visual Content Rules

For real businesses, locations, products, restaurants or architecture:

Do not invent factual visual details.

Do not invent:

buildings

interiors

architecture

signs

logos

landmarks

landscapes

furniture

products

packaging

branding

Prefer real/official imagery when available.

If generating an image:

Research the subject first.

Use real visual references where possible.

Keep the generated result consistent with verified references.

Do not make fictional details look like verified facts.

Generated images should be treated as visual reconstructions when they are not official photographs.

8. Food and Product Images

For food or product imagery:

Research the exact item before generating the image.

Verify:

name

ingredients/specifications

actual appearance

relevant preparation/details

Do not invent ingredients, specifications or product features.

For a series of images, maintain:

consistent composition

consistent lighting

consistent camera perspective

consistent visual language

consistent background treatment

If the user specifies a format such as overhead/top-down, follow it consistently.

9. Menu and Pricing

Use current menu information.

Prefer exact original names when available.

For prices:

use official prices when verified

if the user explicitly requests approximate prices, use ~€XX

never present an estimate as an official price

Do not copy obsolete menu content from the source project merely because it already exists in the code.

10. Internationalization

If the project has multiple languages:

Every content change must be checked in all supported languages.

Preserve:

translation keys

JSON structure

JavaScript expectations

data-i18n attributes

Do not unnecessarily rename translation keys.

Translations must be natural in the target language.

Preserve proper names, geographical names and relevant culinary/product terminology where appropriate.

After changing translations, verify:

required keys exist

JSON is valid

language switching works

no old-brand text remains

11. Contact Information and Links

Never keep contact information from the source project when adapting it to a new business.

Verify:

phone

email

address

website

maps

booking/reservation links

social profiles

Never invent contact details.

Check important CTA destinations after changes.

12. JavaScript and Interaction Safety

Before modifying HTML that may be used by JavaScript:

Check:

selectors

IDs

classes

data-* attributes

event listeners

animation hooks

Do not remove or rename JavaScript hooks without verifying their usage.

Preserve working:

navigation

modals

galleries

scroll interactions

animations

hover states

responsive interactions

13. Responsive Safety

Every meaningful change must be considered for:

desktop

tablet

mobile

Pay special attention to:

hero image cropping

navigation

typography

translated text length

buttons

galleries

modals

image aspect ratios

section spacing

Do not assume desktop changes will work automatically on mobile.

14. Asset Deletion

Never delete an old asset blindly.

Before deleting:

git grep "filename.ext"

Confirm that no relevant references remain.

After deletion/replacement:

git status

Verify that only intended files changed.

15. Source-Brand Cleanup

When creating the new landing page, perform a source-brand audit.

Search for old:

brand name

business name

domain

phone

email

address

social links

image filenames

metadata

copyright

alt text

translation strings

Check:

HTML

CSS

JS

JSON

filenames

comments

metadata

accessibility labels

links

No accidental source-project branding should remain in the final project.

16. SEO

Adapt SEO to the new business.

Check where applicable:

<title>

meta description

canonical

Open Graph

structured data

headings

image alt

internal links

business/location information

Do not keyword-stuff.

Do not put unverified claims into SEO or structured data.

17. Testing

After every meaningful section/change, verify:

page loads

images load

links work

language switching works

animations work

responsive layout works

no obvious console errors

no broken asset references

Do not wait until the end of the project to test.

18. Git

Use small, logical commits.

Before committing:

git status
git diff --stat
git diff

Review deleted and untracked files carefully.

Use descriptive commit messages, for example:

feat: adapt hero content
feat: replace menu content
feat: update landing page imagery
fix: restore mobile navigation
fix: correct image paths

Do not mix unrelated changes in one commit.

19. Deployment

Before pushing:

Review the diff.

Confirm there are no unintended changes.

Check for old-brand references.

Check asset paths.

Check translations.

Check important links.

Commit the changes.

Push to the configured branch.

After deployment:

open the live site

hard refresh

check desktop

check mobile

check language switching

check navigation

check important CTAs

check images

check major animations

20. AI Agent Behavior

The AI agent must work conservatively.

When the user requests:

Analysis only
→ analyze; do not modify files.

One section
→ modify only that section and required dependencies.

Research
→ research and verify before writing factual content.

Image generation
→ research the subject first when factual accuracy matters.

A broader redesign
→ first inspect the architecture and define the affected scope before making changes.

Do not silently expand the task.

Do not perform unrelated cleanup.

Do not rewrite working code simply because another implementation is possible.

21. Final Rule

The project should be evolved, not rebuilt.

Understand
→ Research
→ Verify
→ Change only what was requested
→ Test
→ Review
→ Commit
→ Continue

Preserve working architecture.

Research before writing.

Verify before publishing.

Work one logical section at a time.