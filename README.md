# Website Development Guide

## 1. Project Model

This project is a new website created from an existing ready-made donor project.

The donor project provides the initial HTML structure, CSS architecture, JavaScript architecture, animations, responsive behavior, reusable components, asset structure, multilingual system, visual system and interaction patterns.

The new project should evolve from this foundation.

The donor is not the final website. Its code is used as the technical and visual starting point for the new project.

The development principle is:

> Preserve what works. Adapt what is required.

---

## 2. Donor → New Project Workflow

The standard workflow is:

```text
READY DONOR
    ↓
COPY SOURCE FILES
    ↓
DO NOT COPY .git
    ↓
CREATE NEW PROJECT
    ↓
git init
    ↓
NEW GITHUB REPOSITORY
    ↓
NEW DEPLOYMENT
    ↓
RESEARCH NEW BUSINESS
    ↓
VERIFY INFORMATION
    ↓
ADAPT WEBSITE
    ↓
TEST
    ↓
COMMIT
    ↓
CONTINUE
```

The new project must remain completely independent from the donor project.

---

## 3. Creating a Project from a Donor

When starting a new project from a donor:

1. Obtain the required donor version.
2. Copy the donor source files.
3. Do not copy the donor `.git` directory.
4. Preserve the new project's own `AGENTS.md` and `README.md`.
5. Initialize a new Git repository.
6. Create a new GitHub repository.
7. Configure a new remote.
8. Create the initial commit.
9. Configure independent deployment.
10. Begin adapting the website to the new business.

Example:

```bash
cp -a /path/to/donor/. .
rm -rf .git

git init
git branch -M main
git remote add origin <NEW_REPOSITORY_URL>

git add .
git commit -m "chore: initialize from donor base"
git push -u origin main
```

Never copy donor Git history, remote configuration, deployment credentials, SSH keys or environment secrets.

---

## 4. Project Independence

The new project must have its own:

- Git repository
- Git history
- GitHub repository
- remote
- deployment configuration
- deployment credentials
- project-specific documentation

The donor and new project may share source code, but they must not share repository identity or deployment credentials.

The new project is not a Git fork unless explicitly requested.

---

## 5. Technology

Use the technology already provided by the donor unless a change is explicitly required.

Typical technologies may include:

- HTML5
- CSS3
- Vanilla JavaScript
- ES Modules
- JSON
- SVG
- WebP
- CSS Custom Properties
- Responsive CSS

Do not introduce a new framework simply for convenience.

Avoid unnecessary build systems and dependencies.

---

## 6. Project Structure

The exact structure depends on the donor project.

Typical structure:

```text
/
├── index.html
├── robots.txt
├── sitemap.xml
├── site.webmanifest
├── favicon.ico
├── assets/
├── css/
├── js/
├── data/
└── docs/
```

Always follow the actual donor architecture.

---

## 7. Development Philosophy

The project should be developed incrementally.

Preferred workflow:

```text
Understand
    ↓
Research
    ↓
Verify
    ↓
Plan
    ↓
Adapt one logical section
    ↓
Test
    ↓
Review
    ↓
Commit
    ↓
Continue
```

Do not rewrite the entire website from scratch.

Do not make large unrelated changes.

Do not refactor working code without a clear reason.

---

## 8. Before Development

Before making changes:

1. Read `AGENTS.md`.
2. Read this `README.md`.
3. Inspect the existing project structure.
4. Identify the main HTML entry point.
5. Identify CSS files.
6. Identify JavaScript files.
7. Identify assets.
8. Identify the translation system.
9. Identify external dependencies.
10. Understand the existing architecture.

The donor project is assumed to already be implemented and functional.

A complete functionality audit of the donor is not required unless explicitly requested or there is evidence of a specific problem.

---

## 9. Researching the New Business

Before replacing donor content, research the new business.

Collect verified information such as:

- official business name
- address
- telephone
- email
- website
- social media
- opening hours
- services
- products
- menu
- prices
- history
- location
- architecture
- atmosphere
- important landmarks
- reservation information

Prefer current and authoritative sources.

Priority should generally be:

1. official website
2. official social profiles
3. official business listings
4. official tourism organizations
5. current menus
6. reputable platforms and reviews

Do not publish unverified information as fact.

---

## 10. Content Adaptation

Adapt the website one logical section at a time.

Possible sequence:

1. Global metadata
2. Header
3. Hero
4. About / Place
5. Experience
6. Gallery
7. Cuisine / Products
8. Menu
9. Moments
10. Visit / Location
11. Reservation
12. Footer
13. SEO
14. Final cleanup

The exact order may change depending on the project.

The important rule is:

> One logical section at a time.

---

## 11. HTML

When adapting existing HTML, preserve existing:

- classes
- IDs
- `data-*` attributes
- ARIA attributes
- JavaScript hooks
- DOM relationships
- semantic structure

Before removing or renaming an element, search the repository for references.

Example:

```bash
git grep "element-id"
```

Never assume that an apparently unused class, ID or attribute is unnecessary.

---

## 12. CSS

Reuse the existing CSS architecture.

Prefer:

- existing variables
- existing typography
- existing spacing
- existing breakpoints
- existing utility classes
- existing animation patterns

Avoid duplicate styles.

Do not rewrite the entire stylesheet to solve a local problem.

Do not introduce a CSS framework unless explicitly requested.

---

## 13. JavaScript

Preserve existing JavaScript behavior.

Before changing HTML used by JavaScript, check:

- selectors
- IDs
- classes
- `data-*` attributes
- event listeners
- animation hooks
- modal hooks
- navigation hooks

Existing interactions should continue to work after content replacement.

Do not remove JavaScript-related attributes without checking their usage.

---

## 14. Images and Assets

Every image should have a defined purpose.

Before adding an image:

1. Determine what it represents.
2. Check whether an official or real image exists.
3. Use real imagery where appropriate.
4. If generation is necessary, research the subject first.
5. Maintain visual consistency with the website.

Generated images must not be presented as official photographs.

For real businesses and locations, do not invent architecture, buildings, signs, logos, interiors, furniture, streets, landmarks or branding.

---

## 15. Food and Product Images

For restaurant or product websites, research the actual item before generating imagery.

For food, verify when possible:

- exact dish name
- ingredients
- preparation
- presentation

For products, verify:

- exact model
- dimensions
- specifications
- included accessories
- actual appearance

Do not invent product specifications or ingredients.

Generated imagery should be treated as a visual reconstruction when no suitable official image exists.

---

## 16. Menu and Prices

Use current verified information.

Prefer the original official menu names.

For translations:

- preserve important culinary terminology
- use natural language
- do not translate proper names unnecessarily

For prices:

- use official prices when verified
- use `~€XX` for approximate prices
- never present an estimate as an official price

---

## 17. Multilingual Content

If the project supports multiple languages, every content change must be reflected in all supported languages.

After changing content:

- verify every translation key exists
- verify all language files are updated
- verify JSON syntax
- verify language switching
- verify no donor content remains in secondary languages

Translations should sound natural to native speakers.

Do not translate word-for-word when that creates unnatural language.

---

## 18. Contact Information

All donor contact information must be replaced.

Check the entire repository for:

- phone numbers
- email addresses
- domains
- addresses
- map links
- reservation links
- social media
- external services
- business names

Search globally:

```bash
git grep -i "old-domain"
git grep -i "old-business-name"
git grep -i "old-email"
```

No donor contact information should remain in the final project.

---

## 19. SEO

SEO should be adapted after the main content is established.

Check:

- `<title>`
- meta description
- canonical
- Open Graph metadata
- structured data
- semantic headings
- image `alt` attributes
- internal links
- sitemap
- robots.txt

SEO content must reflect verified information.

Avoid keyword stuffing.

---

## 20. Responsive Design

Every major change must be considered for:

- desktop
- tablet
- mobile

Pay particular attention to:

- hero image cropping
- typography
- long translations
- buttons
- navigation
- galleries
- modals
- image aspect ratios
- section spacing

Preserve the donor's responsive system unless there is a clear reason to change it.

---

## 21. Animations

Preserve existing:

- scroll animations
- reveal animations
- image transitions
- hover states
- modal transitions
- gallery movement
- parallax effects
- section transitions

Do not replace animation logic unless required.

After changing animated content, verify that the animation still works.

---

## 22. Asset Cleanup

Do not delete donor assets simply because they are no longer visible.

Before deleting an asset:

```bash
git grep "filename.ext"
```

Confirm that there are no remaining references.

Then remove it.

After cleanup:

```bash
git status
```

Review the changed files carefully.

---

## 23. Testing

After every meaningful change, verify:

- page loads
- images load
- links work
- language switching works
- animations work
- mobile layout works
- desktop layout works
- no obvious console errors
- no broken asset references

Do not wait until the end of the project to discover problems.

---

## 24. Git Workflow

Use small, logical commits.

Before committing:

```bash
git status
git diff --stat
git diff
```

Example:

```bash
git add .
git commit -m "feat: adapt hero for new business"
git push origin main
```

Good commit messages describe the actual change.

Examples:

```text
feat: adapt hero content
feat: replace restaurant imagery
feat: update menu content
feat: add multilingual menu translations
fix: restore mobile navigation
fix: correct image paths
docs: update project documentation
```

Avoid unrelated changes in the same commit.

---

## 25. Deployment

The new project must have an independent deployment.

Typical deployment may use:

- GitHub Pages
- another static hosting provider
- a custom hosting environment

Before deployment:

```bash
git status
git diff --stat
```

Confirm:

- no unintended files changed
- no donor references remain
- no broken asset paths
- translations are complete
- important links are correct

After deployment:

1. Open the live website.
2. Perform a hard refresh.
3. Check desktop.
4. Check mobile.
5. Check language switching.
6. Check navigation.
7. Check important CTAs.
8. Check images.
9. Check major animations.

---

## 26. Deployment Credentials

Never copy deployment credentials from the donor project.

Do not reuse:

- SSH keys
- access tokens
- API keys
- deployment secrets
- environment secrets
- hosting credentials

Configure new credentials for the new project.

Credentials must never be committed to Git.

---

## 27. Final Pre-Launch Checklist

### Brand

- correct brand name
- correct logo
- correct colors
- correct typography
- no donor branding

### Content

- no placeholders
- no obsolete information
- no invented facts
- correct business information

### Images

- all images load
- correct image paths
- consistent visual style
- no accidental donor imagery

### Links

- navigation works
- CTAs work
- phone links work
- maps work
- reservation links work
- external links work
- no donor-domain links remain

### Languages

- all translations exist
- no missing keys
- no donor content
- language switcher works

### Responsive

- desktop
- tablet
- mobile

### Accessibility

- semantic headings
- meaningful button labels
- meaningful link labels
- image alt text
- keyboard navigation
- modal accessibility
- focus behavior

### SEO

- title
- meta description
- headings
- canonical
- Open Graph
- structured data
- image alt text
- sitemap
- robots.txt

---

## 28. AI-Assisted Development

When working with an AI coding assistant:

1. Read `AGENTS.md`.
2. Read `README.md`.
3. Inspect the relevant files.
4. Understand the existing implementation.
5. Identify dependencies.
6. Research required information.
7. Verify factual information.
8. Make the smallest reasonable change.
9. Test the result.
10. Review the changes.
11. Commit the change.
12. Continue with the next logical section.

If the user requests only analysis:

> Do not modify files.

If the user requests only one section:

> Do not modify unrelated sections.

If information is uncertain:

> Research or ask. Do not invent.

---

## 29. Relationship Between README.md and AGENTS.md

`README.md` describes the project and its development workflow.

`AGENTS.md` defines the rules that must be followed when modifying the project.

They complement each other.

`README.md` should explain:

- what the project is
- how it is structured
- how it is created
- how it is developed
- how it is tested
- how it is deployed

`AGENTS.md` should define:

- mandatory development rules
- donor handling rules
- content verification rules
- Git rules
- asset rules
- AI behavior
- safety constraints
- pre-launch requirements

Do not duplicate unnecessary instructions between the two files.

---

## 30. Golden Rule

The project should evolve, not be rebuilt.

The donor provides the foundation.

The new project provides the new identity.

Preserve working architecture.

Research before writing.

Verify before publishing.

Change one logical section at a time.

Test after every meaningful change.

Keep the new project independent from the donor.

Keep commits small and understandable.

Preferred workflow:

```text
DONOR
  ↓
UNDERSTAND
  ↓
RESEARCH
  ↓
VERIFY
  ↓
ADAPT
  ↓
TEST
  ↓
REVIEW
  ↓
COMMIT
  ↓
CONTINUE
```
