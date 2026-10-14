---
file: ui-kit.md
brand: Niwart
version: 0.9
updated: 2026-10-14
owner: Arty
inherits: 00-core-niwart.md
overrides: core 4 (weights) — `eyebrow` uses Plus Jakarta Sans 700, see 1.2
covers: UI kit (web and product interfaces)
source: Figma — Branding library (text styles, grid styles)
---

# Niwart — UI kit

<!-- Файл ассета. Наследует всё из 00-core-niwart.md.
     Цвета и шрифты — только ссылки на токены core по имени. Здесь живут размеры, роли, сетка и компоненты UI.
     Размеры кегля и сетка взяты из Figma (библиотека Branding). Веса — из core, а не из Figma:
     в Figma есть стили Bold и ExtraLight Italic, но core разрешает только 400, 500 и 500 italic.
     Всё, что помечено TBD, в Figma не найдено — заполнить вручную. -->

## 1. Typography

### 1.1 Font families

| Token (core) | Family | Weight | Web font stack |
|---|---|---|---|
| `font-heading` | Plus Jakarta Sans | 500 | `"Plus Jakarta Sans", Arial, sans-serif` |
| `font-body` | Plus Jakarta Sans | 400 | `"Plus Jakarta Sans", Arial, sans-serif` |
| `font-accent` | Plus Jakarta Sans | 500 italic | `"Plus Jakarta Sans", Arial, sans-serif` |

- **Loading (MUST):** load from Google Fonts only 400, 500, 500 italic and 700 (700 — for `eyebrow` only).
- **Fallback:** Arial — Regular for 400, Bold for 500, Italic for 500 italic, Bold for 700.
- **Units:** sizes are given in px; rem = px / 16.

### 1.2 Type roles

<!-- Размеры и интерлиньяж — из описаний текстовых стилей Figma. Колонка «Figma style» — исходное имя стиля. -->

**Headings** — `font-heading`, letter spacing 0

| Role | Figma style | Desktop size / line height | Mobile size / line height |
|---|---|---|---|
| `h1` | `Title/Desktop/H1/Regular`, `Title/Mobile/H1/Regular` | 48 / 64 px | 32 / 40 px |
| `h2` | `Title/Desktop/H2/Regular`, `Title/Mobile/H2` | 40 / 52 px | 28 / 36 px |
| `h3` | `Title/Desktop/H3/Regular`, `Title/Mobile/H3` | 32 / 40 px | 26 / 32 px |
| `h4` | `Title/Desktop/H4`, `Title/Mobile/H4` | 24 / 32 px | 22 / 28 px |
| `h5` | `Title/Desktop/H5`, `Title/Mobile/H5` | 20 / 28 px | 20 / 28 px |

**Body** — `font-body`, letter spacing 0, same on desktop and mobile

| Role | Figma style | Size / line height | Use for |
|---|---|---|---|
| `body-l` | `Paragraph/L` | 16 / 28 px | Default body text |
| `body-m` | `Paragraph/M` | 14 / 24 px | Secondary text, dense layouts |
| `caption` | `Paragraph/S (caption)` | 12 / 20 px | Captions, footnotes, meta |

**Labels** — `font-heading`, letter spacing 0, same on desktop and mobile

| Role | Figma style | Size / line height | Use for |
|---|---|---|---|
| `label-l` | `Label/L/Bold` | 18 / 24 px | Navigation |
| `label-m` | `Label/M/Bold` | 16 / 20 px | Form labels |
| `label-s` | `Label/S/Bold` | 14 / 18 px | Tags |

**Eyebrow** — short uppercase label above a heading; same on desktop and mobile

| Role | Font | Weight | Size / line height | Letter spacing | Case |
|---|---|---|---|---|---|
| `eyebrow` | Plus Jakarta Sans | 700 | 12 px / normal | 2 px | uppercase (`text-transform: uppercase`) |

- **Override (core 4):** `eyebrow` is the only role allowed to use weight 700.
- **Color (MUST):** `primary` on `white` / `bg-subtle`; `primary-variant` on `bg-dark`; `white` on `primary`.
- MUST be placed directly above a heading (`h1`–`h4`), max one per heading, max ~4 words.
- MUST NOT be used as running text or as a replacement for a heading.

<!-- В Figma label-стили называются Bold; по core `font-heading` = 500, поэтому лейблы используют 500. -->
<!-- В Figma есть стили `Title/*/ExtraLight Italic` (H1–H3) — это старые выделения.
     По core выделение = `font-accent` (500 italic) + `primary`, поэтому отдельные стили не нужны.
     `Title/Mobile/H1/ExtraLight Italic` в Figma имеет 48 / 64 px, больше мобильного H1 — похоже на ошибку. -->

### 1.3 Text colors by role

| Role | On `white` / `bg-subtle` | On `bg-dark` | On `primary` |
|---|---|---|---|
| `h1`–`h5` | `text-high` | `text-inverse-high` | `white` |
| `body-l`, `body-m`, `caption` | `text-medium` | `text-inverse-medium` | `white` |
| `label-*` | `text-high` | `text-inverse-high` | `white` |
| `eyebrow` | `primary` | `primary-variant` | `white` |
| Disabled | `text-low` | `text-inverse-low` | — |

### 1.4 Type rules

- MUST use only the roles from 1.2; no custom sizes.
- MUST NOT skip heading levels for visual size; pick the role, not the size.
- MUST NOT center-align body text longer than 2 lines. Left-align by default.
- SHOULD keep line length of `body-l` within 60–80 characters.
- Text highlights follow core section 4: `font-accent` + `primary` (on `bg-dark` — `primary-variant`), at the size of the surrounding role.
- Numbers in tables SHOULD use tabular figures (`font-variant-numeric: tabular-nums`).

## 2. Layout grid

<!-- Из стилей сетки Figma: `Desktop` и `Mobile`. Планшетная сетка и брейкпоинты в Figma не найдены. -->

| Grid | Figma style | Columns | Column | Gutter | Margin |
|---|---|---|---|---|---|
| Desktop | `Desktop` | 12 | 80 px | 24 px | auto (centered) |
| Tablet | — | TBD | TBD | TBD | TBD |
| Mobile | `Mobile` | 4 | auto (fluid) | 24 px | 24 px |

- **Desktop container:** 12 × 80 + 11 × 24 = 1224 px, centered.
- **Breakpoints:** TBD (desktop / tablet / mobile).

## 3. Spacing and shape

- **Spacing scale:** TBD. Gutters in section 2 suggest a base of 8 px (8 / 16 / 24 / 32 / 48 / 64) — confirm before use.
- **Corner radius:** TBD (buttons, cards, tags, inputs).
- **Shadows:** TBD.

## 4. Components

### 4.1 Tags and statuses

| Variant | Fill | Text | Text role |
|---|---|---|---|
| Neutral tag | `surface` | `text-high` | `label-s` |
| Category tag | `accent-yellow`, `accent-teal`, `accent-indigo`, `accent-purple`, `accent-pink` | color from «Text on tag» in core 3.4 | `label-s` |
| Status — error / risk | `accent-red` | `text-high` | `label-s` |
| Status — warning | `accent-orange` | `text-high` | `label-s` |
| Status — success | `accent-green` | `text-high` | `label-s` |

- MUST follow core section 2: max 3 accent colors per layout, one meaning per color, more categories → neutral tags.
- Padding, height and radius: TBD.

### 4.2 Buttons

<!-- Источник истины для кнопок — этот файл, не Figma. Компонент `.button` в Figma (Design Library, node 9203:3365) может отличаться; при расхождении прав этот файл. -->

**Anatomy:** text label + optional trailing arrow icon (`east`, 20 × 20 px). Both «with arrow» and «without arrow» are allowed.

| Property | Value |
|---|---|
| Shape | Pill, radius 50 px |
| Padding | 24 px horizontal, 10 px vertical (same with or without arrow) |
| Gap (text → icon) | 10 px |
| Text | `font-body` 400, 14 / 20 px |
| Border (outline variants) | 1.5 px, inside |
| Height — `sm` | 40 px |
| Height — `lg` | 52 px |
| Width | Hug content; full width allowed on the mobile grid (content centered) |

**Variants** — default state

| Variant | Use on | Fill | Border | Text and icon |
|---|---|---|---|---|
| Primary | `white`, `bg-subtle` | `bg-dark` | — | `white` |
| Secondary | `white`, `bg-subtle` | none | 1.5 px `primary` | `text-high` |
| Ghost | `white`, `bg-subtle` | none | — | `primary` |
| Primary on dark | `bg-dark` | none | 1.5 px `gradient-neo` | `white` |
| Secondary on dark | `bg-dark` | none | 1.5 px `text-inverse-low` | `text-inverse-high` |
| Ghost on dark | `bg-dark` | none | — | `primary-variant` |
| Inverse | `primary`, `bg-dark` | `white` | — | `text-high` |

**States**

| State | Primary, Secondary, Secondary on dark | Ghost | Ghost on dark | Primary on dark | Inverse |
|---|---|---|---|---|---|
| Hover | fill `primary`, border `primary`, text `white` | fill `bg-subtle` on `white`, fill `white` on `bg-subtle`; text unchanged | label underlined, colors unchanged | fill `gradient-neo`, text `white` | fill `bg-subtle` |
| Pressed | as hover + scale 0.98 | as hover + scale 0.98 | as hover + scale 0.98 | as hover + scale 0.98 | fill `surface-pressed` + scale 0.98 |
| Focus (keyboard) | default + ring 2 px, offset 2 px: `primary` on light, `primary-variant` on dark | ring `primary` | ring `primary-variant` | ring `primary-variant` | ring `white` on `primary`, `primary-variant` on `bg-dark` |
| Disabled | no fill, border 1.5 px + text: `surface-pressed` / `text-low` on light, `text-inverse-low` on dark | text `text-low` | text `text-inverse-low` | border and text `text-inverse-low` | no fill, border 1.5 px and text: `surface-pressed` on `primary`, `text-inverse-low` on `bg-dark` |

- **Motion:** 120 ms, `cubic-bezier(.2, 0, 0, 1)` for fill, border and scale. With `prefers-reduced-motion: reduce` — no transition, no scale.
- **Focus (MUST):** show the ring on keyboard focus only (`:focus-visible`), never remove it.
- **Disabled (MUST):** no hover, pressed or focus; cursor `not-allowed`.
- **Hierarchy (SHOULD):** one Primary (or Primary on dark / Inverse) per section; Secondary and Ghost for the rest.
- **Gradient:** `gradient-neo` is allowed only in the Primary on dark button: as the border (default) and as the fill (hover, pressed) (core 3.5).
- **Contrast exception:** `white` text and icon on `gradient-neo` in hover and pressed are exempt from the contrast rule (core 3.5).

**Icon button**

Circular button with one icon and no label.

| Property | Value |
|---|---|
| Shape | Circle |
| Size — `sm` / `lg` | 40 × 40 px / 52 × 52 px |
| Icon | 20 × 20 px, centered |
| Variants and states | Same as the text button: each icon button variant inherits fill, border, icon color and all states from the button variant of the same name (Primary, Secondary, Ghost, Primary on dark, Secondary on dark, Ghost on dark, Inverse). Ghost on dark hover: fill `primary`, icon `white` (no label to underline). |

- **Accessible name (MUST):** every icon button has a text label for screen readers (`aria-label`) and a tooltip with the same text.

### 4.3 Other components

| Component | Status |
|---|---|
| Inputs | TBD |
| Cards | TBD |
| Navigation | TBD |
| Tables | TBD |

## 5. Changelog

- 0.9 — 2026-10-14 — Ghost hover on light backgrounds: fill swaps to the other light background (`bg-subtle` on `white`, `white` on `bg-subtle`); Ghost on dark keeps the underline. Review: label roles no longer mention buttons (buttons use `font-body` 14 / 20); Inverse disabled on `bg-dark` uses `text-inverse-low`.
- 0.8 — 2026-10-14 — Buttons: added Ghost, Ghost on dark, Secondary on dark, Inverse and Icon button; arrow made optional; full width allowed on mobile; hierarchy rule added.
- 0.7 — 2026-10-14 — Button states added: hover (`primary` fill; `gradient-neo` fill on dark), pressed (as hover + scale 0.98), focus ring, disabled; motion 120 ms with reduced-motion fallback.
- 0.6 — 2026-10-14 — Buttons: this file is the source of truth, not Figma; Figma naming question removed.
- 0.5 — 2026-10-14 — Buttons rebuilt as three variants, default state only: Primary (`bg-dark` fill), Secondary (`primary` border, `text-high`), Primary on dark (`gradient-neo` border, `white`); hover, disabled and hover motion removed.
- 0.4 — 2026-10-14 — Buttons: `gradient-neo` fill and contrast exception moved to core 1.7; disabled on dark set to `text-inverse-low` (border and text); `lg` height 52 px on all backgrounds; label weight 500 per core; open questions reduced to naming.
- 0.3 — 2026-10-14 — Buttons rebuilt from Figma Design Library (`.button`): anatomy, sizes, states on light and dark backgrounds, hover motion; conflicts with core listed as open questions.
- 0.2 — 2026-10-14 — Added `eyebrow` role (12 px, 700, uppercase, letter spacing 2 px, `primary`); weight 700 declared as override of core 4.
- 0.1 — 2026-10-14 — First version: type roles (desktop and mobile) and layout grid from Figma Branding library; text colors by role; tags and statuses; button variants from core tokens; open questions marked TBD.
