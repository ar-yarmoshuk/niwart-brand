---
file: ui-kit.md
brand: Niwart
version: 0.24
updated: 2026-10-18
owner: Arty
inherits: 00-core-niwart.md
overrides: core 4 (weights) — `eyebrow` uses Plus Jakarta Sans 700, `approach-text` uses 300 Light, see 1.2
covers: UI kit (web and product interfaces)
source: Figma — Branding library (text styles, grid styles); Design Library (inputs, node 9210:585)
---

# Niwart — UI kit

<!-- Файл ассета. Наследует всё из 00-core-niwart.md.
     Цвета и шрифты — только ссылки на токены core по имени. Здесь живут размеры, роли, сетка и компоненты UI.
     Размеры кегля и сетка взяты из Figma (библиотека Branding). Веса — из core, а не из Figma:
     в Figma есть стили Bold и ExtraLight Italic, но core разрешает только 400, 500 и 300 italic.
     Всё, что помечено TBD, в Figma не найдено — заполнить вручную. -->

## 1. Typography

### 1.1 Font families

| Token (core) | Family | Weight | Web font stack |
|---|---|---|---|
| `font-heading` | Plus Jakarta Sans | 500 (> 32 px), 400 (≤ 32 px) | `"Plus Jakarta Sans", Arial, sans-serif` |
| `font-body` | Plus Jakarta Sans | 400; 300 (`approach-text` only) | `"Plus Jakarta Sans", Arial, sans-serif` |
| `font-accent` | Plus Jakarta Sans | 300 italic | `"Plus Jakarta Sans", Arial, sans-serif` |

- **Loading (MUST):** load from Google Fonts only 300, 400, 500, 300 italic and 700 (300 upright — for `approach-text` only, 700 — for `eyebrow` only).
- **Fallback:** Arial — Regular for 300 and 400, Bold for 500, Italic for 300 italic, Bold for 700.
- **Units:** sizes are given in px; rem = px / 16.

### 1.2 Type roles

<!-- Размеры и интерлиньяж — из описаний текстовых стилей Figma. Колонка «Figma style» — исходное имя стиля.
     Десктопные заголовки с 0.21 заданы здесь (72 / 44 / 32 / 28 / 24) и расходятся с Figma; мобильные — по Figma. -->

**Headings** — `font-heading`, letter spacing 0. Weight by size: > 32 px — 500 Medium, ≤ 32 px — 400 Regular (core 4).

| Role | Figma style | Desktop size / line height | Desktop weight | Mobile size / line height | Mobile weight |
|---|---|---|---|---|---|
| `h1` | `Title/Desktop/H1/Regular`, `Title/Mobile/H1/Regular` | 72 / 80 px | 500 | 32 / 40 px | 400 |
| `h2` | `Title/Desktop/H2/Regular`, `Title/Mobile/H2` | 44 / 52 px | 500 | 28 / 36 px | 400 |
| `h3` | `Title/Desktop/H3/Regular`, `Title/Mobile/H3` | 32 / 40 px | 400 | 26 / 32 px | 400 |
| `h4` | `Title/Desktop/H4`, `Title/Mobile/H4` | 28 / 36 px | 400 | 22 / 28 px | 400 |
| `h5` | `Title/Desktop/H5`, `Title/Mobile/H5` | 24 / 32 px | 400 | 20 / 28 px | 400 |

**Body** — `font-body` 400, letter spacing 0, line height 150%, same on desktop and mobile

| Role | Figma style | Size / line height | Use for |
|---|---|---|---|
| `body-l` | — | 24 / 36 px | Text paired with `h1` |
| `body-m` | — | 20 / 30 px | Text paired with `h2`–`h5`; default body text |
| `body-s` | — | 18 / 27 px | Button text, input value |
| `caption` | `Paragraph/S (caption)` | 12 / 20 px | Captions, footnotes, meta, input labels, helper text |

**Labels** — `font-body` (400 Regular), letter spacing 0, same on desktop and mobile

| Role | Figma style | Size / line height | Use for |
|---|---|---|---|
| `label-l` | `Label/L/Bold` | 18 / 24 px | Navigation |
| `label-m` | `Label/M/Bold` | 16 / 20 px | UI labels |
| `label-s` | `Label/S/Bold` | 14 / 18 px | Tags |

**Quote**

| Role | Font | Weight | Size / line height | Letter spacing |
|---|---|---|---|---|
| `quote` | `font-accent` | 300 italic | 32 / 48 px (150%) | 0 |

- Mobile size: TBD.

**Approach** — a highlight pair: `h5` title + large light description

| Role | Font | Weight | Size / line height | Letter spacing |
|---|---|---|---|---|
| `approach-title` | `font-heading` (role `h5`) | as `h5` | as `h5` | 0 |
| `approach-text` | `font-body` | 300 Light | 44 / 66 px (150%) | 0 |

- **Approach pair (MUST):** `approach-text` is used only directly under an `approach-title` (`h5`); an `approach-title` is always followed by `approach-text`. Use the pair to highlight a key statement (approach, principle, value).
- **Override (core 4):** `approach-text` is the only role allowed to use upright 300 Light.
- Mobile size of `approach-text`: TBD.

**Eyebrow** — short uppercase label above a heading; same on desktop and mobile

| Role | Font | Weight | Size / line height | Letter spacing | Case |
|---|---|---|---|---|---|
| `eyebrow` | Plus Jakarta Sans | 700 | 12 px / normal | 2 px | uppercase (`text-transform: uppercase`) |

- **Override (core 4):** `eyebrow` is the only role allowed to use weight 700.
- **Color (MUST):** `primary` on `white` / `bg-subtle`; `primary-variant` on `bg-dark`; `white` on `primary`.
- MUST be placed directly above a heading (`h1`–`h4`), max one per heading, max ~4 words.
- MUST NOT be used as running text or as a replacement for a heading.

<!-- В Figma label-стили называются Bold; в ui-kit лейблы используют `font-body` 400 Regular. -->
<!-- В Figma есть стили `Title/*/ExtraLight Italic` (H1–H3) — это старые выделения.
     По core выделение = `font-accent` (300 Light Italic) + `primary` (на `bg-dark` — `gradient-neo`), поэтому отдельные стили не нужны.
     `Title/Mobile/H1/ExtraLight Italic` в Figma имеет 48 / 64 px, больше мобильного H1 — похоже на ошибку. -->

### 1.3 Text colors by role

| Role | On `white` / `bg-subtle` | On `bg-dark` | On `primary` |
|---|---|---|---|
| `h1`–`h5` | `text-high` | `text-inverse-high` | `white` |
| `body-l`, `body-m`, `body-s`, `caption` | `text-medium` | `text-inverse-medium` | `white` |
| `quote`, `approach-text` | `text-high` | `text-inverse-high` | `white` |
| `label-*` | `text-high` | `text-inverse-high` | `white` |
| `eyebrow` | `primary` | `primary-variant` | `white` |
| Disabled | `text-low` | `text-inverse-low` | — |

### 1.4 Type rules

- MUST use only the roles from 1.2; no custom sizes.
- **Heading–text pairs (MUST):** text directly under `h1` uses `body-l`; under `h2`–`h5` — `body-m`; under `approach-title` — `approach-text`.
- MUST NOT skip heading levels for visual size; pick the role, not the size.
- MUST NOT center-align body text longer than 2 lines. Left-align by default.
- SHOULD keep line length of `body-l` and `body-m` within 60–80 characters.
- Text highlights follow core section 4: `font-accent` + `primary` (on `bg-dark` — `font-accent` + `gradient-neo`), at the size of the surrounding role.
- **Gradient text:** `background: <gradient-neo>; -webkit-background-clip: text; background-clip: text; color: transparent`. The gradient spans the highlighted words, not the whole line.
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
- **Corner radius:** `radius-s` — 8 px (neutral tag, card icon button); buttons and icon buttons — pill / circle (4.2); other radii TBD.
- **Shadows:** `shadow-xs` — `0 0 2px rgba(5, 7, 13, 0.05)` (neutral tag); other shadows TBD.

## 4. Components

### 4.1 Tags and statuses

<!-- Нейтральный тег: Figma Website, компонент `nw/Tag`, node 8244:10274
     (https://www.figma.com/design/D60XCEWqi6XfVQJy7aFK2K/Website?node-id=8244-10274).
     В Figma обводка `surface-pressed` с прозрачностью 77% и иконка `text-high` с прозрачностью 70% — приведены к токенам core. -->

**Neutral tag**

| Property | Value |
|---|---|
| Fill | `white` |
| Border | 1 px `surface-pressed`, inside |
| Shadow | `shadow-xs` (section 3) |
| Radius | `radius-s` — 8 px |
| Padding | 8 px horizontal, 6 px vertical |
| Height | 32 px |
| Gap (icon → text) | 8 px |
| Icon | optional, 15 × 15 px, `text-medium`; e.g. [`assets/icons/code-xml.svg`](assets/icons/code-xml.svg) |
| Text | `label-s` (`font-body` 400, 14 / 18 px), uppercase, `text-high` |
| Use on | `white`, `bg-subtle` |

**Category tags and statuses**

| Variant | Fill | Text | Text role |
|---|---|---|---|
| Category tag | `accent-yellow`, `accent-teal`, `accent-indigo`, `accent-purple`, `accent-pink` | color from «Text on tag» in core 3.4 | `label-s` |
| Status — error / risk | `accent-red` | `text-high` | `label-s` |
| Status — warning | `accent-orange` | `text-high` | `label-s` |
| Status — success | `accent-green` | `text-high` | `label-s` |

- MUST follow core section 2: max 3 accent colors per layout, one meaning per color, more categories → neutral tags.
- Category tags and statuses: padding, height and radius — TBD.

### 4.2 Buttons

<!-- Источник истины для кнопок — этот файл, не Figma. Компонент `.button` в Figma (Design Library, node 9203:3365) может отличаться; при расхождении прав этот файл. -->

**Anatomy:** text label + optional trailing arrow icon ([`assets/icons/arrow.svg`](assets/icons/arrow.svg), 20 × 20 px, `currentColor` — takes the text color). Both «with arrow» and «without arrow» are allowed.

| Property | Value |
|---|---|
| Shape | Pill, radius 50 px |
| Padding | 24 px horizontal, 10 px vertical (same with or without arrow) |
| Gap (text → icon) | 10 px |
| Text | `body-s` size (`font-body` 400, 18 px), line height 20 px inside the button |
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
| Ghost on dark | `bg-dark` | none | — | `gradient-neo` |
| Inverse | `primary` | `white` | — | `text-high` |

**States**

| State | Primary, Secondary | Secondary on dark | Ghost | Ghost on dark | Primary on dark | Inverse |
|---|---|---|---|---|---|---|
| Hover | fill `primary`, border `primary`, text `white` | no fill, border 1.5 px `gradient-neo`, text `white` | fill `bg-subtle` on `white`, fill `white` on `bg-subtle`; text unchanged | fill `white-5`, text unchanged | fill `gradient-neo`, text `white` | fill `bg-subtle` |
| Pressed | as hover + scale 0.98 | as hover + scale 0.98 | as hover + scale 0.98 | as hover + scale 0.98 | as hover + scale 0.98 | fill `surface-pressed` + scale 0.98 |
| Focus (keyboard) | default + ring 2 px, offset 2 px, `primary` | default + ring 2 px, offset 2 px, `primary-variant` | ring `primary` | ring `primary-variant` | ring `primary-variant` | ring `white` |
| Disabled | no fill, border 1.5 px `surface-pressed`, text `text-low` | no fill, border 1.5 px and text `text-inverse-low` | text `text-low` | text `text-inverse-low` | border and text `text-inverse-low` | no fill, border 1.5 px and text `surface-pressed` |

- **Motion:** 120 ms, `cubic-bezier(.2, 0, 0, 1)` for fill, border and scale. With `prefers-reduced-motion: reduce` — no transition, no scale.
- **Focus (MUST):** show the ring on keyboard focus only (`:focus-visible`), never remove it.
- **Disabled (MUST):** no hover, pressed or focus; cursor `not-allowed`.
- **Hierarchy (SHOULD):** one Primary (or Primary on dark / Inverse) per section; Secondary and Ghost for the rest.
- **Gradient:** `gradient-neo` is allowed only on `bg-dark`: Primary on dark border (default) and fill (hover, pressed); Secondary on dark border (hover, pressed); Ghost on dark text; icon button states below (core 3.5).
- **Contrast exceptions (core 3.5):** `white` text and icon on `gradient-neo` in hover and pressed; Ghost on dark `gradient-neo` text on `white-5` in hover and pressed (≈ 4.2:1 at the start).

**Icon button**

Circular button with one icon and no label.

| Property | Value |
|---|---|
| Shape | Circle |
| Size — `sm` / `lg` | 40 × 40 px / 52 × 52 px |
| Icon | 20 × 20 px, centered |
| Variants and states | Same as the text button: each icon button variant inherits fill, border, icon color and all states from the button variant of the same name (Primary, Secondary, Ghost, Primary on dark, Secondary on dark, Ghost on dark, Inverse). Exceptions below. |
| Ghost on dark — default | icon `white` |
| Ghost on dark — hover, pressed | fill `white-5`, icon `gradient-neo` |

- **Accessible name (MUST):** every icon button has a text label for screen readers (`aria-label`) and a tooltip with the same text.

**Card icon button**

<!-- Figma Website, `Icon button`, node 8244:10401
     (https://www.figma.com/design/D60XCEWqi6XfVQJy7aFK2K/Website?node-id=8244-10401).
     Состояния в Figma не заданы — добавлены здесь по логике кнопок. -->

Small square icon button that opens a card or its details («open», «read more»).

| Property | Value |
|---|---|
| Shape | Square, `radius-s` — 8 px |
| Size | 32 × 32 px |
| Icon | 16 × 16 px, centered; [`assets/icons/maximize.svg`](assets/icons/maximize.svg) |
| Use on | Cards on `white` / `bg-subtle` |

| State | Fill | Border | Icon |
|---|---|---|---|
| Default | `white` | 1 px `surface-pressed` | `text-high` |
| Hover | `primary` | 1 px `primary` | `white` |
| Pressed | as hover + scale 0.98 | | |
| Focus (keyboard) | default + ring 2 px `primary`, offset 2 px | | |
| Disabled | `white` | 1 px `surface-pressed` | `text-low` |

- **Use (MUST):** only inside a card that has no Ghost button, as its open / read more action; one per card. A card with a Ghost button uses the Ghost button instead.
- **Accessible name (MUST):** `aria-label` names the action and the card, e.g. «Open: Websites».

### 4.3 Inputs

<!-- Источник: Figma Design Library, компоненты `.input` и `.input--marker`, node 9210:585
     (https://www.figma.com/design/LlgbPskb7DPtCqc7paueZW/Design-Library?node-id=9210-585).
     Цвета приведены к токенам core. В Figma текст поля набран Inter — заменён на `font-body` (core 4).
     Подпись над полем, цвет плейсхолдера, вариант для `bg-dark` и цвета иконок маркера в Figma нет — добавлены здесь. -->

**Anatomy:** label above + value text (or placeholder) + underline + status marker on the right; optional helper text below the underline, replaced by the error message in the error state. No box, no fill.

| Property | Value |
|---|---|
| Style | Underline only, no fill, no border box |
| Width | Fluid (Figma: 290 px) |
| Label | `caption` (`font-body` 400, 12 / 20 px), 8 px above the value |
| Field height | 28 px: text 20 px + gap 8 px + underline |
| Text (value) | `body-s` size (`font-body` 400, 18 px), line height 20 px inside the field |
| Placeholder | Example of the expected input, e.g. «Full Name»; disappears while typing. MUST NOT replace the label |
| Underline | 1 px, full width |
| Marker | 20 × 20 px circle, right edge, vertically centered on the text line |
| Helper text / error message | `caption` (`font-body` 12 / 20 px), 2 px below the underline; one line; the error message replaces the helper text |

**Colors**

| Element | On `white` / `bg-subtle` | On `bg-dark` |
|---|---|---|
| Label | `text-high` | `text-inverse-high` |
| Value | `text-high` | `text-inverse-high` |
| Placeholder | `text-low` | `text-inverse-low` |
| Helper text | `text-medium` | `text-inverse-medium` |
| Error message | `text-high` | `text-inverse-high` |

**States**

| State | Underline — light | Underline — dark | Marker |
|---|---|---|---|
| Default | `text-low` | `text-inverse-low` | empty circle, 1 px border: `surface-pressed` on light, `text-inverse-low` on dark |
| Hover | `text-high` | `text-inverse-high` | empty circle |
| Active (focus) | `primary` | `primary-variant` | empty circle |
| Error | `accent-red` | `accent-red` | fill `accent-red`, «!» icon `text-high` + error message below |
| Success | as default | as default | fill `primary`, check icon `white` |
| Disabled | `text-low` | `text-inverse-low` | hidden |

- **Marker** is a separate component (`.input--marker`) with three states: default (empty), valid (check), error («!»). Error icon color follows core 3.4 «Text on tag»; success uses `primary` with a `white` icon (core 3.5: `white` on `primary` ≈ 5.6:1).
- **Active** is shown both on click and on keyboard focus; the `primary` / `primary-variant` underline is the focus indicator.
- **Error (MUST):** the signal is the red underline and marker; the message text stays `text-high` / `text-inverse-high` (core 3.5: no accents as running text).
- **Disabled (MUST):** label, value, placeholder and helper text in `text-low` (on `bg-dark` — `text-inverse-low`); no hover, focus or marker; cursor `not-allowed`.
- **Contrast:** the default underline `text-low` ≈ 3.1:1 on `white` (passes 3:1 for a field boundary), ≈ 2.9:1 on `bg-subtle`; on `bg-dark` `text-inverse-low` ≈ 3.1:1.

### 4.4 Other components

| Component | Status |
|---|---|
| Cards | TBD |
| Navigation | TBD |
| Tables | TBD |

## 5. Changelog

- 0.24 — 2026-10-18 — Neutral tag redesigned from Figma Website (`white` fill, `surface-pressed` border, `shadow-xs`, 8 px radius, optional icon, uppercase `label-s`); added `radius-s` and `shadow-xs`; button arrow is now [`assets/icons/arrow.svg`](assets/icons/arrow.svg); added card icon button (32 px square, `maximize` icon) for cards without a Ghost button; icons stored in `assets/icons/`.
- 0.23 — 2026-10-18 — Body scale: `body-l` 24 / 36 (with `h1`), `body-m` 20 / 30 (with `h2`–`h5`), `body-s` 18 / 27 (buttons, input value); heading–text pair rule; added `quote` (32 / 48, 300 italic) and the approach pair (`h5` title + `approach-text` 44 / 66, 300 Light); button and input text 18 px with 20 px line height.
- 0.22 — 2026-10-15 — Body scale rewritten: `body-l` 18 / 28 (default, paragraphs), `body-m` 16 / 24 (cards), new `body-s` 14 / 20 px; Figma Paragraph styles no longer match.
- 0.21 — 2026-10-15 — Desktop heading scale changed: h1 72 / 80, h2 44 / 52, h3 32 / 40, h4 28 / 36, h5 24 / 32 px (line heights on a 4 px grid); heading weight by size: > 32 px 500 Medium, ≤ 32 px 400 Regular.
- 0.20 — 2026-10-14 — Label roles (`label-l`, `label-m`, `label-s`) switched from `font-heading` 500 to `font-body` 400 Regular; tags follow.
- 0.19 — 2026-10-14 — Inputs: success marker fill `primary` with `white` check icon (was `accent-green`).
- 0.18 — 2026-10-14 — Inputs: label role changed from `label-m` to `caption`.
- 0.17 — 2026-10-14 — Inputs: default and disabled underline on light backgrounds changed to `text-low`.
- 0.16 — 2026-10-14 — Inputs: default and disabled underline on light backgrounds changed to `bg-subtle`.
- 0.15 — 2026-10-14 — Inputs: disabled state and helper text added; open questions closed.
- 0.14 — 2026-10-14 — Inputs: default underline `surface-pressed`; error message in `text-high`; label (`label-m`) above the field and placeholder in `text-low`; `bg-dark` variant from existing tokens; success marker `accent-green`; marker icons `text-high`.
- 0.13 — 2026-10-14 — Inputs added from Figma Design Library (`.input`, `.input--marker`): anatomy, sizes, states (default, hover, active, error, success), marker; Inter replaced with `font-body`; open questions listed.
- 0.12 — 2026-10-14 — Ghost on dark hover fill (button and icon button): `white-10` → `white-5`.
- 0.11 — 2026-10-14 — Secondary on dark (button and icon button): hover and pressed use a 1.5 px `gradient-neo` border instead of a fill; Secondary on dark gets its own column in the states table.
- 0.10 — 2026-10-14 — `font-accent` 300 Light Italic; highlights on `bg-dark` use `gradient-neo` (gradient text); Ghost on dark: `gradient-neo` text, hover fill `white-10` instead of underline; icon button: Secondary on dark hover fill `gradient-neo`, Ghost on dark icon `white` and hover fill `white-10` with `gradient-neo` icon; Inverse limited to `primary` backgrounds.
- 0.9 — 2026-10-14 — Ghost hover on light backgrounds: fill swaps to the other light background (`bg-subtle` on `white`, `white` on `bg-subtle`); Ghost on dark keeps the underline. Review: label roles no longer mention buttons (buttons use `font-body` 14 / 20); Inverse disabled on `bg-dark` uses `text-inverse-low`.
- 0.8 — 2026-10-14 — Buttons: added Ghost, Ghost on dark, Secondary on dark, Inverse and Icon button; arrow made optional; full width allowed on mobile; hierarchy rule added.
- 0.7 — 2026-10-14 — Button states added: hover (`primary` fill; `gradient-neo` fill on dark), pressed (as hover + scale 0.98), focus ring, disabled; motion 120 ms with reduced-motion fallback.
- 0.6 — 2026-10-14 — Buttons: this file is the source of truth, not Figma; Figma naming question removed.
- 0.5 — 2026-10-14 — Buttons rebuilt as three variants, default state only: Primary (`bg-dark` fill), Secondary (`primary` border, `text-high`), Primary on dark (`gradient-neo` border, `white`); hover, disabled and hover motion removed.
- 0.4 — 2026-10-14 — Buttons: `gradient-neo` fill and contrast exception moved to core 1.7; disabled on dark set to `text-inverse-low` (border and text); `lg` height 52 px on all backgrounds; label weight 500 per core; open questions reduced to naming.
- 0.3 — 2026-10-14 — Buttons rebuilt from Figma Design Library (`.button`): anatomy, sizes, states on light and dark backgrounds, hover motion; conflicts with core listed as open questions.
- 0.2 — 2026-10-14 — Added `eyebrow` role (12 px, 700, uppercase, letter spacing 2 px, `primary`); weight 700 declared as override of core 4.
- 0.1 — 2026-10-14 — First version: type roles (desktop and mobile) and layout grid from Figma Branding library; text colors by role; tags and statuses; button variants from core tokens; open questions marked TBD.
