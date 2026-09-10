Website Development Guide

1. Project Overview

This project is a modern landing page based on an existing website foundation.

The existing project should be treated as the technical and visual starting point.

The goal is to progressively adapt the website to the new brand, business, content and visual identity while preserving the existing functionality and architecture wherever possible.

The project should be developed incrementally rather than rewritten from scratch.

2. Development Philosophy

The main principle is:

Preserve what works. Change only what is required.

The existing website may already contain HTML, CSS, JavaScript, animations, transitions, responsive layouts, galleries, modals, navigation, multilingual support and reusable components.

These should be preserved unless there is a clear reason to change them.

Avoid unnecessary refactoring.

Avoid changing architecture simply for stylistic reasons.

Avoid replacing working implementations with new technologies unless explicitly requested.

3. Development Workflow

All development should follow this sequence:

AUDIT
  ↓
RESEARCH
  ↓
VERIFY
  ↓
PLAN
  ↓
ADAPT ONE SECTION
  ↓
TEST
  ↓
REVIEW
  ↓
COMMIT
  ↓
NEXT SECTION

Do not skip directly from the request to a large implementation.

Each meaningful change should be isolated and verified before moving to the next part of the website.

4. Step 1 — Audit the Existing Project

Before making changes, inspect the project.

Read:

AGENTS.md
README.md

Then inspect:

HTML
CSS
JavaScript
assets/
data/
i18n/
fonts/

Identify:

main HTML entry point

page sections

CSS files

JavaScript files

reusable components

animations

scroll interactions

responsive rules

translation system

image structure

external dependencies

Understand how the website works before modifying it.

5. Step 2 — Identify the Existing Page Structure

Map the current page into sections.

For example:

Header
Hero
About / Place
Experience
Gallery
Cuisine / Products
Menu
Moments
Visit / Location
Reservation
Footer

The actual structure depends on the project.

Do not assume that every project uses the same sections.

The important thing is to understand the existing structure before changing it.

6. Step 3 — Research the New Brand

Before replacing content, research the new business or brand.

Collect verified information about:

official name

location

address

telephone

website

social media

services

products

menu

history

atmosphere

architecture

important landmarks

opening information

other relevant business information

Prefer:

official sources

official social profiles

official tourism organizations

official maps/business information

current menus

reputable review platforms

Do not rely on old information if current information is available.

7. Step 4 — Verify Information

Before publishing factual information, verify it.

Important information includes:

addresses

phone numbers

URLs

prices

opening hours

menu items

ingredients

historical dates

business history

location claims

architectural descriptions

If something cannot be verified, do not present it as fact.

Use neutral wording or leave it out.

Never invent missing business information.

8. Step 5 — Adapt the Website One Section at a Time

Work sequentially.

Example:

1. Global metadata
2. Header
3. Hero
4. Place / About
5. Experience
6. Gallery
7. Cuisine / Products
8. Menu
9. Moments
10. Visit
11. Reservation
12. Footer
13. SEO
14. Final cleanup

The exact order can change depending on the project.

The important rule is:

One logical section at a time.

Do not simultaneously redesign unrelated sections.

9. HTML Rules

When adapting an existing section:

Preserve existing:

classes

IDs

data-* attributes

ARIA attributes

JavaScript hooks

DOM relationships

semantic structure

unless there is a specific reason to change them.

Before removing or renaming an element, search the JavaScript and CSS for references.

Never assume an apparently unused attribute is actually unused.

10. CSS Rules

Reuse the existing CSS system.

Prefer:

existing variables

existing spacing system

existing typography

existing breakpoints

existing animation timings

existing utility patterns

Avoid creating duplicate styles when an existing style can be reused.

Do not introduce a CSS framework unless explicitly requested.

Do not rewrite the entire stylesheet for a single section.

11. JavaScript Rules

Preserve existing JavaScript behavior.

Before changing HTML used by JavaScript, identify:

selectors

IDs

classes

data-* attributes

event listeners

animation hooks

Do not remove JavaScript-related attributes without checking their usage.

Existing interactions should continue working after content replacement.

12. Images and Assets

Every new image should have a clear purpose.

Before creating or downloading an image:

Determine what the image represents.

Check whether an official/real image exists.

Use a real image when appropriate.

If generation is necessary, research the subject first.

Use real references when available.

Maintain visual consistency with the rest of the website.

Generated imagery should not accidentally be presented as an official photograph.

13. Real Locations and Businesses

When creating visual content for a real business or location:

Do not invent:

buildings

signs

logos

architecture

interiors

furniture

landscapes

streets

landmarks

business branding

Use verified visual references.

If the exact environment cannot be reproduced reliably, create an atmospheric interpretation without making unsupported factual claims.

14. Food and Product Photography

For restaurant or product websites, research the actual item before generating an image.

For food, verify:

exact dish name

ingredients

preparation

presentation when available

For products, verify:

model

dimensions

specifications

included accessories

actual appearance

Do not add invented ingredients or product features.

When a generated image is used because no suitable official image exists, it should function as a visual reconstruction.

Maintain consistency across the entire image series.

15. Menu and Pricing

When creating menu content:

Use current information.

Prefer exact original menu names when available.

For translations, preserve important culinary terminology where appropriate.

For prices:

use official prices when verified

if only approximate prices are available, clearly indicate them

use ~€XX for approximate prices

never present an estimate as an official price

16. Multilingual Content

If the project supports multiple languages, every content change must be reflected in all supported languages.

After changing content:

check that every translation key exists

check that all languages are updated

check that the JSON structure remains valid

check that language switching still works

Do not leave old-brand text inside secondary languages.

17. Translation Style

Translations should sound natural to native speakers.

Do not translate word-for-word when this produces unnatural language.

Preserve proper names, product names, culinary terms and geographic names when appropriate.

18. Contact Information

Replace all source-project contact information.

Check:

phone

email

website

address

Google Maps

reservation links

social media

external services

Search the entire repository for old information.

No source-project contact information should remain in the final website.

19. SEO

Adapt SEO after the core content is established.

Check:

<title>

meta description

canonical if present

Open Graph metadata if present

structured data if present

semantic headings

image alt attributes

internal links

Do not over-optimize or stuff keywords.

SEO content must reflect verified business information.

20. Responsive Design

Every major change must be considered for:

desktop

tablet

mobile

Pay particular attention to:

hero image cropping

typography

long translations

buttons

navigation

galleries

modals

image aspect ratios

section spacing

Preserve the existing responsive system.

21. Animations

Preserve existing:

scroll animations

reveal animations

image transitions

hover states

modal transitions

gallery movement

parallax effects

section transitions

Do not replace animation logic unless necessary.

After changing animated content, verify that the animation still works.

22. Asset Cleanup

Do not delete old files simply because they are no longer visible.

Before deleting an asset:

git grep "filename.ext"

Confirm that there are no remaining references.

Then remove the asset.

After cleanup:

git status

Check that only intended files changed.

23. Testing After Each Section

After completing a section, check:

page loads

images load

links work

language switching works

animations work

mobile layout works

desktop layout works

no obvious console errors

no broken asset references

Do not wait until the end of the project to test everything.

24. Git Workflow

Use small, logical commits.

Before committing:

git status
git diff --stat
git diff

For new files:

git status

Review deleted files carefully.

Example:

git add .
git commit -m "feat: adapt hero for new brand"
git push origin main

Good commit messages describe the actual change.

Examples:

feat: adapt hero content
feat: replace restaurant imagery
feat: update menu content
feat: add multilingual menu translations
fix: restore mobile navigation
fix: correct image paths

Avoid commits containing unrelated changes.

25. Deployment

Deploy only after the current work has been reviewed.

Before pushing:

git status
git diff --stat

Confirm:

no unintended files changed

no old-brand references remain

no broken asset paths

translations are complete

important links are correct

Then commit and push.

After deployment:

wait for the hosting platform

open the live website

perform a hard refresh

check desktop

check mobile

check language switching

check navigation

check important CTAs

check images

check major animations

26. Final Pre-Launch Audit

Brand

correct brand name

correct logo

correct colors

correct typography

no source-brand references

Content

no placeholder content

no obsolete information

no invented facts

correct business information

Images

all images load

correct image paths

consistent visual style

no accidental source-project images

Links

navigation works

CTAs work

phone links work

maps work

external links work

no old-domain links

Languages

all translations exist

no missing keys

no old content

language switcher works

Responsive

desktop

tablet

mobile

Accessibility

semantic headings

button labels

link labels

image alt text

keyboard navigation

modal accessibility

focus behavior

SEO

title

meta description

headings

canonical

Open Graph

structured data

image alt text

27. AI-Assisted Development

When working with an AI coding assistant:

inspect the relevant files

understand the existing implementation

identify dependencies

research required information

make the smallest reasonable change

verify the result

move to the next requested step

If the user requests only analysis, do not modify files.

If the user requests only one section, do not modify unrelated sections.

If information is uncertain, research or ask rather than invent.

28. Golden Rule

The project should evolve, not be rebuilt.

Preserve the existing architecture.

Research before writing.

Verify before publishing.

Change one logical section at a time.

Test after every meaningful change.

Keep commits small and understandable.

Preferred workflow:

Understand
→ Research
→ Verify
→ Adapt
→ Test
→ Review
→ Commit
→ Continue