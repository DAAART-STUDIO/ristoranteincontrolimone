# Design System

## Purpose

This document defines the visual language, design principles and implementation rules for the Ristorante Incontro Limone website.

The design system provides a consistent visual foundation while allowing individual sections to maintain their own editorial composition and storytelling.

The system should evolve incrementally as the project is adapted and finalized.

---

## Direction

Ristorante Incontro Limone is designed as a premium editorial hospitality experience.

Visual references:

* contemporary Italian hospitality
* architecture
* refined restaurant design
* travel editorial
* cinematic photography
* Lake Garda atmosphere
* Italian landscape
* contemporary print and magazine design

The interface should never feel like a generic restaurant template.

The visual identity should be communicated primarily through:

* photography
* typography
* composition
* whitespace
* visual rhythm
* subtle motion
* atmosphere

---

## Brand Character

The visual language should feel:

* refined
* Italian
* atmospheric
* contemporary
* elegant
* warm
* editorial
* confident
* understated

Avoid a visual direction that feels:

* corporate
* generic
* overly commercial
* visually noisy
* excessively decorative
* template-driven

---

## Principles

Prioritize:

* photography
* typography
* composition
* whitespace
* hierarchy
* atmosphere
* visual rhythm
* subtle motion
* editorial storytelling
* accessibility
* responsive composition

Avoid:

* excessive cards
* excessive rounded corners
* generic gradients
* excessive shadows
* unnecessary borders
* excessive badges
* unnecessary UI
* template-like layouts
* dense dashboard-style interfaces
* decorative elements without purpose
* excessive animation
* inconsistent spacing
* arbitrary colors

---

# Typography

Typography is one of the primary elements of the visual identity.

The existing typography system should be preserved unless there is an explicit requirement to change it.

## Display Typography

The display typeface is used for:

* hero headlines
* major section titles
* editorial statements
* large visual text
* selected decorative typography

Existing design token:

```text id="m4a9hr"
--font-display
```

Display typography should create visual character and should not be used for dense body content.

---

## Body Typography

Body typography is used for:

* descriptions
* paragraphs
* navigation
* labels
* metadata
* interface controls

Body text must prioritize readability across desktop and mobile layouts.

---

## Typography Hierarchy

The general hierarchy should follow:

1. Hero / primary statement
2. Section heading
3. Supporting heading
4. Introductory text
5. Body text
6. Metadata / labels
7. Utility text

Typography values should use the existing design tokens wherever possible.

Avoid arbitrary font sizes inside individual components when an appropriate token already exists.

---

## Typography Rules

* Maintain clear hierarchy between display and body typography.
* Use generous line-height for readable content.
* Avoid excessively long text lines.
* Preserve hierarchy on mobile.
* Avoid unnecessary uppercase text.
* Use letter spacing intentionally.
* Do not sacrifice readability for visual styling.
* Ensure localized text can expand without breaking the layout.

---

# Color System

The color system is implemented through CSS custom properties in:

```text id="w1rq1y"
css/tokens.css
```

The existing theme architecture should be preserved while the visual identity is progressively adapted for Ristorante Incontro Limone.

Colors should support:

* readability
* hierarchy
* atmosphere
* photography
* section separation
* interaction states

The palette should remain restrained.

Photography and typography should remain the dominant visual elements.

---

## Theme Support

Theme behavior is handled by:

```text id="y8v0yz"
js/modules/theme-switcher.js
```

Theme-specific values should be implemented through CSS custom properties rather than duplicated component styles.

Components should consume semantic theme variables instead of defining independent colors.

---

# Spacing

Spacing establishes the rhythm of the editorial layout.

Spacing should be consistent across:

* sections
* headings
* paragraphs
* navigation
* buttons
* galleries
* content groups
* interface elements

Use existing spacing tokens defined in `css/tokens.css`.

Avoid introducing arbitrary spacing values when an existing token provides the required value.

---

## Editorial Spacing

Large editorial sections should have sufficient vertical space to create rhythm and atmosphere.

Spacing does not need to be mathematically identical between sections.

Intentional variation is allowed when it improves composition and storytelling.

---

# Layout

The main layout system is implemented through:

```text id="qbr3m2"
css/layout.css
```

with component-specific styles located in:

```text id="o6n5c7"
css/components/
```

The layout should support:

* full-width sections
* constrained content areas
* asymmetric compositions
* large photography
* overlapping elements
* editorial grids
* responsive stacking
* cinematic compositions

---

## Composition

The visual system favors editorial composition over rigid component layouts.

Preferred techniques include:

* asymmetric alignment
* controlled negative space
* large image areas
* intentional cropping
* visual overlaps
* varying content widths
* strong vertical rhythm

Composition must remain predictable and usable on smaller screens.

---

# Grid

The grid provides structural consistency without forcing every section into an identical layout.

Individual sections may use different compositions when required by the content.

Avoid turning every section into:

* cards
* identical columns
* repetitive content blocks
* dashboard-like grids

The grid should support the story rather than dominate it.

---

# Components

Reusable component styles are located in:

```text id="3z8u7w"
css/components/
```

Components should be:

* focused
* reusable
* responsive
* theme-aware
* predictable
* accessible

Before creating a new component:

1. Check whether an existing component can be reused.
2. Check existing design tokens.
3. Preserve established spacing and typography.
4. Keep component-specific styles inside the appropriate stylesheet.
5. Avoid unnecessary variants.

---

# Buttons and Actions

Buttons and interactive controls should remain visually restrained.

Primary actions may be used for:

* reservations
* visit information
* navigation
* important calls to action

Interactive controls should provide appropriate:

* default state
* hover state
* focus state
* active state
* disabled state where applicable

Not every link needs to be presented as a prominent button.

---

# Navigation

Navigation should remain minimal and editorial.

Navigation behavior is implemented through:

```text id="m0wz1q"
js/modules/navigation.js
js/modules/header.js
```

Navigation should prioritize:

* orientation
* clarity
* readability
* predictable interaction
* responsive behavior

Mobile navigation should be optimized for touch interaction rather than simply being a smaller desktop menu.

---

# Imagery

Photography is a central part of the design system.

Images should communicate:

* restaurant atmosphere
* cuisine
* location
* Lake Garda
* hospitality
* people and moments where appropriate

Photography should feel authentic and editorial.

Avoid generic stock imagery when representative project photography is available.

---

## Image Composition

Images may use:

* cinematic crops
* full-width compositions
* asymmetric layouts
* portrait formats
* landscape formats
* controlled overlays
* responsive cropping

Image composition should support the content and should not reduce readability.

---

## Image Performance

Images should be optimized for:

* file size
* dimensions
* responsive rendering
* mobile bandwidth
* loading performance

WebP should be preferred where appropriate.

Meaningful images should have descriptive `alt` attributes.

Decorative images should use an empty `alt` attribute where appropriate.

---

# Motion

Motion reinforces the cinematic and editorial character of the website.

Animation should communicate:

* transition
* hierarchy
* spatial relationships
* interaction
* progression

Animation should not exist purely for decoration.

---

## Motion Principles

Animations should be:

* subtle
* purposeful
* smooth
* responsive
* performant

Avoid:

* excessive movement
* distracting loops
* unnecessary parallax
* long blocking transitions
* animation that interferes with reading
* animation that interferes with navigation

---

## Animation Implementation

Shared animation styles are located in:

```text id="o7f7kt"
css/animations.css
```

JavaScript animation behavior should remain isolated in dedicated modules.

GSAP / ScrollTrigger may be used for selected cinematic interactions.

Animations should respect reduced-motion preferences where applicable.

---

# Scroll Behavior

Scroll-based interactions are part of the editorial experience.

Relevant functionality includes:

```text id="q8l4bd"
js/modules/smooth-scroll.js
js/modules/scroll-progress.js
js/modules/scroll-morph.js
```

Scroll effects should enhance storytelling and orientation without making normal page navigation difficult.

---

# Interaction States

Interactive elements should provide clear states.

Relevant controls should account for:

* default
* hover
* focus
* active
* disabled

Keyboard focus must remain visible.

Touch interactions must remain usable on mobile devices.

---

# Accessibility

Accessibility is part of the design system.

The interface should provide:

* semantic HTML
* logical heading hierarchy
* accessible navigation
* keyboard accessibility
* visible focus states
* meaningful image alternatives
* sufficient text contrast
* correctly labelled controls
* accessible modal behavior
* reduced-motion support where applicable

Visual effects must never make essential content inaccessible.

---

# Responsive Design

The website is designed for:

* desktop
* tablet
* mobile

Responsive behavior should preserve the intended visual hierarchy rather than simply shrinking desktop layouts.

---

## Responsive Principles

On smaller screens:

* typography must remain readable
* navigation must remain accessible
* images should use appropriate crops
* content should stack naturally
* horizontal overflow should be avoided
* controls must remain usable
* animations must remain performant
* spacing should adapt to available space

Mobile may use a different composition from desktop when required.

---

# Light and Dark Modes

The project supports theme switching.

Theme behavior is handled by:

```text id="qf4l3w"
js/modules/theme-switcher.js
```

Theme values should remain centralized in:

```text id="d6k3p2"
css/tokens.css
```

When adding or modifying a component, verify its appearance in every supported theme.

---

# Internationalization

The design system must support the project's multilingual architecture.

Localized content is stored in:

```text id="s7a1x4"
data/i18n/
```

Internationalization behavior is handled by:

```text id="h6p2wd"
js/modules/i18n.js
```

Supported languages currently include:

* Italian
* English
* German

The interface must accommodate different text lengths between languages.

Do not build fixed-width components around text that only works in one language.

---

# Icons

Icons are stored in:

```text id="d7x6h1"
assets/icons/
```

Prefer existing icons before creating new ones.

New icons should match the established:

* visual weight
* proportions
* stroke / fill language
* scale
* spacing

Avoid mixing unrelated icon styles.

---

# Modals

Modal interfaces should be used only where they provide a clear functional benefit.

Current modal-related functionality includes:

```text id="r5k9v2"
js/modules/reservation-modal.js
js/modules/product-modal.js
```

Modals should:

* clearly communicate their purpose
* be easy to close
* support keyboard interaction
* remain usable on mobile
* preserve visual consistency
* prevent inappropriate background interaction

---

# Content and Design Relationship

Design should support the content rather than compensate for weak content.

Restaurant content should influence:

* hierarchy
* image selection
* section rhythm
* emphasis
* composition

Do not add decorative elements simply to fill empty space.

Whitespace is an intentional part of the visual system.

---

# Design Tokens

The central design-token layer is:

```text id="v8b1m6"
css/tokens.css
```

Tokens should be used for shared values such as:

* colors
* typography
* spacing
* borders
* radii
* transitions
* layout constraints
* theme values

Before introducing a new global value, check whether an existing token can be reused.

New tokens should have a clear semantic purpose.

---

# CSS Organization

The CSS architecture is:

```text id="z4d6h9"
css/
├── reset.css
├── tokens.css
├── base.css
├── layout.css
├── animations.css
└── components/
```

Responsibilities:

### `reset.css`

Browser normalization and baseline reset.

### `tokens.css`

Design tokens, CSS custom properties and theme values.

### `base.css`

Global typography and foundational element styles.

### `layout.css`

Page-level layout and structural rules.

### `animations.css`

Shared animation and transition rules.

### `components/`

Reusable component-specific styles.

---

# Design Change Rules

When modifying the visual system:

1. Check existing tokens first.
2. Check existing components before creating new ones.
3. Preserve the established visual language.
4. Avoid unnecessary global changes.
5. Test all supported themes.
6. Test desktop and mobile layouts.
7. Test interactive states.
8. Check animation performance.
9. Check accessibility.
10. Keep changes limited to the requested scope.

Do not perform broad visual refactors without an explicit requirement.

---

# Incremental Adaptation

The project is being progressively adapted for Ristorante Incontro Limone.

Visual changes should therefore be incremental.

When replacing existing project content or branding:

* preserve working layout structures where possible
* preserve functional JavaScript
* preserve responsive behavior
* preserve established animation systems
* replace project-specific visual content deliberately
* avoid unrelated refactoring

A working component should not be rewritten simply because its original implementation came from an earlier project.

---

# Source of Truth

The actual repository implementation is the source of truth for the current design system.

This document should describe the design rules that are currently implemented or intentionally established for the project.

When significant visual architecture changes are made, update this document.

Do not document hypothetical visual features as if they were already implemented.

---

# Design Goal

The final experience should feel like a coherent digital identity for Ristorante Incontro Limone.

The objective is not to make every section identical.

The objective is to ensure that every section belongs to the same visual world while retaining its own editorial purpose.
