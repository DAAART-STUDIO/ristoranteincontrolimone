# Architecture

## Overview

Ristorante Incontro Limone is a lightweight static website built with HTML, CSS and vanilla JavaScript.

The project intentionally avoids a frontend framework and does not currently require a build step.

The architecture is based on a modular static frontend with separate layers for:

* semantic HTML structure
* visual styling
* design tokens
* responsive layout
* JavaScript behavior
* internationalized content
* static assets

The project is designed to preserve the existing working architecture while the website content, branding and restaurant-specific information are progressively adapted for Ristorante Incontro Limone.

---

## Stack

* HTML5
* CSS3
* Vanilla JavaScript
* JavaScript ES Modules
* JSON
* SVG
* WebP
* CSS Custom Properties
* Responsive CSS
* GSAP / ScrollTrigger where required for cinematic interactions

There is currently:

* no React
* no Vue
* no Tailwind
* no required frontend framework
* no required build step

---

## Project Structure

```text
ristoranteincontrolimone/
├── assets/
│   ├── icons/
│   ├── images/
│   └── logo/
│
├── css/
│   ├── components/
│   ├── animations.css
│   ├── base.css
│   ├── layout.css
│   ├── reset.css
│   └── tokens.css
│
├── data/
│   └── i18n/
│       ├── de.json
│       ├── en.json
│       └── it.json
│
├── docs/
│   ├── ARCHITECTURE.md
│   ├── DEPLOYMENT.md
│   ├── DESIGN-SYSTEM.md
│   ├── I18N.md
│   └── README.md
│
├── js/
│   ├── modules/
│   ├── app.js
│   └── config.js
│
├── .gitignore
├── .nojekyll
├── AGENTS.md
├── README.md
├── favicon.ico
├── index.html
├── robots.txt
├── site.webmanifest
└── sitemap.xml
```

The structure above reflects the current repository architecture.

---

# Directory Responsibilities

## `assets/`

Contains static visual assets used by the website.

```text
assets/
├── icons/
├── images/
└── logo/
```

### `assets/icons/`

Contains interface and decorative icons.

Icons should be reused where possible instead of introducing duplicate assets.

### `assets/images/`

Contains website photography and other raster visual assets.

Production images should represent the actual restaurant, cuisine, location or other verified project content.

### `assets/logo/`

Contains logo and brand assets used by the website.

---

## `css/`

Contains the visual system, page layout, responsive rules, components and animations.

```text
css/
├── components/
├── animations.css
├── base.css
├── layout.css
├── reset.css
└── tokens.css
```

### `reset.css`

Provides browser normalization and baseline reset rules.

### `tokens.css`

Contains CSS custom properties used as the central design-token layer.

Typical token categories include:

* colors
* typography
* spacing
* borders
* radii
* transitions
* layout values
* theme values

### `base.css`

Contains global element styling and foundational typography rules.

### `layout.css`

Contains page-level layout and structural rules.

### `animations.css`

Contains shared animation and transition styles.

### `components/`

Contains component-specific styles.

Component styles should remain focused on their respective UI elements and should not become a replacement for global layout rules.

---

# `data/`

Contains structured content data.

```text
data/
└── i18n/
    ├── de.json
    ├── en.json
    └── it.json
```

The `i18n` directory contains localized website content.

Italian is currently the default language.

English and German are supported through separate translation files.

The translation structure should remain synchronized between all supported languages.

---

# `js/`

Contains the JavaScript application layer.

```text
js/
├── modules/
├── app.js
└── config.js
```

## `app.js`

Acts as the main JavaScript entry point.

It initializes the required application functionality and connects the individual modules.

## `config.js`

Contains shared frontend configuration constants.

Configuration values should be centralized here when they are used across multiple JavaScript modules.

Configuration includes areas such as:

* default theme
* supported languages
* language persistence
* theme persistence
* reduced-motion detection
* navigation breakpoint

Project-specific configuration values should be updated when the corresponding production functionality is adapted.

---

# `js/modules/`

The JavaScript functionality is divided into focused modules.

The current module set includes:

```text
js/modules/
├── cuisine.js
├── dashboard.js
├── dishes-wheel.js
├── earth-scene.js
├── experience.js
├── header.js
├── i18n.js
├── moments.js
├── navigation.js
├── observer.js
├── particles.js
├── product-modal.js
├── radar-effect.js
├── reservation-modal.js
├── roadmap-render.js
├── scroll-morph.js
├── scroll-progress.js
├── smooth-scroll.js
├── theme-switcher.js
└── view-gallery.js
```

Modules should remain focused on their specific responsibility.

Examples:

* `navigation.js` — navigation behavior
* `header.js` — header behavior
* `i18n.js` — internationalization
* `theme-switcher.js` — theme switching
* `smooth-scroll.js` — smooth scrolling
* `scroll-progress.js` — scroll progress
* `scroll-morph.js` — scroll-based visual transformations
* `reservation-modal.js` — reservation interface
* `view-gallery.js` — gallery behavior
* `moments.js` — moments section behavior
* `experience.js` — experience section behavior
* `cuisine.js` — cuisine-related interactions

Existing modules should be reused before creating new ones.

---

# HTML Architecture

`index.html` is the main document and contains the semantic page structure.

The HTML layer is responsible for:

* page structure
* semantic sections
* navigation
* content containers
* accessibility attributes
* SEO metadata
* structured data where applicable
* JavaScript hooks
* module loading

When adapting existing HTML, preserve working:

* classes
* IDs
* `data-*` attributes
* ARIA attributes
* JavaScript hooks
* DOM relationships

Before removing or renaming an element, verify that it is not referenced by CSS or JavaScript.

---

# Data Flow

The general application flow is:

```text
index.html
    │
    ├── CSS
    │   ├── reset.css
    │   ├── tokens.css
    │   ├── base.css
    │   ├── layout.css
    │   ├── components/
    │   └── animations.css
    │
    └── js/app.js
            │
            ├── js/config.js
            │
            └── js/modules/
                    │
                    ├── navigation
                    ├── header
                    ├── i18n
                    ├── theme
                    ├── scrolling
                    ├── galleries
                    ├── section interactions
                    ├── modals
                    └── visual effects
```

Localized content is loaded through the i18n layer from:

```text
data/i18n/
```

---

# Internationalization

Internationalization is handled through:

```text
js/modules/i18n.js
```

with localized content stored in:

```text
data/i18n/
```

Supported languages:

* Italian — `it`
* English — `en`
* German — `de`

Italian is the default language.

The translation system should remain independent from the visual presentation layer.

Language-specific content should be stored in the appropriate JSON files instead of being duplicated throughout JavaScript modules.

---

# Theme Architecture

The website supports theme switching.

Theme behavior is handled by:

```text
js/modules/theme-switcher.js
```

Theme values are implemented through CSS custom properties in:

```text
css/tokens.css
```

Components should consume the existing theme variables instead of defining independent theme systems.

---

# Responsive Architecture

The website is designed for:

* desktop
* tablet
* mobile

Responsive behavior is primarily implemented through CSS.

JavaScript should only introduce viewport-specific behavior when CSS alone is insufficient.

Responsive changes must preserve:

* visual hierarchy
* navigation usability
* image composition
* typography
* interactive controls
* modal usability
* animation performance

---

# Animation Architecture

The project uses CSS and JavaScript-driven animation.

Shared animation styles are located in:

```text
css/animations.css
```

JavaScript animation and interaction logic is implemented through dedicated modules.

GSAP / ScrollTrigger may be used where required for cinematic or scroll-based interactions.

Animation logic should remain isolated from unrelated application logic.

Animations must not interfere with:

* navigation
* reading
* accessibility
* responsive behavior
* page performance

---

# Modal Architecture

The project contains dedicated modules for modal interfaces.

Current modal-related modules include:

```text
js/modules/reservation-modal.js
js/modules/product-modal.js
```

Modal behavior should remain isolated from unrelated application logic.

Modals must remain usable on desktop and mobile and should preserve keyboard and accessibility behavior.

---

# Asset Architecture

Static assets are separated from application logic.

```text
assets/
├── icons/
├── images/
└── logo/
```

Asset references should remain compatible with the current deployment model.

Before removing an asset, search the repository for references.

Example:

```bash
git grep "filename.ext"
```

Unused assets should only be removed after confirming that no references remain.

---

# SEO and Metadata

SEO-related information is primarily defined in the main HTML document and supporting root-level files.

Relevant project files include:

```text
index.html
robots.txt
sitemap.xml
site.webmanifest
favicon.ico
```

SEO metadata must represent the current restaurant project.

This includes:

* page title
* meta description
* canonical URL
* Open Graph metadata
* structured data
* language information
* image metadata

Restaurant-specific factual information must be verified before publication.

---

# External Dependencies

The project intentionally uses a lightweight frontend architecture.

Dependencies should remain minimal.

Do not introduce a frontend framework or build system unless there is a clear project requirement.

Existing libraries should not be replaced or removed merely for stylistic reasons.

---

# Development Principles

The project should evolve incrementally.

The preferred approach is:

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

The existing working architecture should be preserved wherever possible.

Avoid:

* rewriting the website from scratch
* unnecessary framework migrations
* broad CSS rewrites
* unrelated refactoring
* removing working JavaScript
* changing architecture without a concrete requirement

---

# Separation of Concerns

The project follows a clear separation between:

### Structure

`index.html`

### Presentation

`css/`

### Behavior

`js/`

### Content

`data/i18n/`

### Static Assets

`assets/`

### Documentation

`docs/`

This separation should be preserved as the project evolves.

---

# Architectural Change Rules

When changing the architecture:

1. Inspect the existing implementation first.
2. Check whether an existing module already solves the problem.
3. Reuse existing CSS tokens and components.
4. Preserve existing JavaScript hooks.
5. Avoid unnecessary new dependencies.
6. Keep changes limited to the requested scope.
7. Test desktop and mobile behavior.
8. Test all supported languages when localized content is affected.
9. Update the relevant documentation when architecture changes.

---

# Source of Truth

The actual repository implementation is the source of truth for the architecture.

Documentation must describe the implementation that currently exists in the repository.

If the architecture changes, update this document accordingly.

Do not document planned functionality as if it were already implemented.

---

# Project Independence

This repository has its own:

* Git repository
* Git history
* remote
* documentation
* deployment configuration
* project identity

The project must remain independent from any donor project used as its technical starting point.

Donor repository history, credentials and deployment configuration must never be reused.

---

# Local Development

Because the project uses JavaScript ES Modules, `index.html` should not be opened directly with `file://`.

Use a local HTTP server.

### Python

```bash
cd ristoranteincontrolimone
python -m http.server 8002
```

Then open:

```text
http://localhost:8002
```

---

# Architectural Goal

The project should remain:

* lightweight
* modular
* maintainable
* responsive
* accessible
* performant
* visually consistent
* independent from its donor source

The core principle is:

> Preserve the working architecture. Adapt the implementation incrementally for Ristorante Incontro Limone.