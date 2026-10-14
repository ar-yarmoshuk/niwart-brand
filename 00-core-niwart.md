---
file: 00-core-niwart.md
brand: Niwart
version: 1.20
updated: 2026-10-14
owner: Arty
source: Figma — Branding, node 622:1633 (https://www.figma.com/design/K1KuS3pyAeyVi8kAVHyfb3/Branding?node-id=622-1633); gradient — node 712:1291 (https://www.figma.com/design/K1KuS3pyAeyVi8kAVHyfb3/Branding?node-id=712-1291)
role: Single source of truth. All asset files inherit from this file.
---

# Niwart — Core

<!-- Этот файл хранит ТОЛЬКО то, что одинаково для всех материалов.
     Размеры кегля, сетки, форматы и компоненты живут в файлах ассетов
     (ui-kit.md и т.д.). Токены в файлах ассетов не дублируются —
     только ссылки по имени: `primary`, `font-heading`, `text-high`.
     Цвета и шрифт взяты из Figma. Всё, что помечено TBD, в Figma не найдено — заполнить вручную. -->

## 0. How to use this file

- Asset files MUST reference tokens by name, never by raw value.
- Asset files MAY override a rule only by listing it under `Overrides:` in their header.
- If an asset file and this file conflict and no override is declared, this file wins.
- MUST = never break. SHOULD = default, break only with a stated reason.

## 1. Brand essence

- **Audience:** TBD
- **Personality:** TBD · TBD · TBD
- **Tone of voice:** TBD
- **Visual summary:** TBD

## 2. Global hard rules

- MUST use only colors defined in section 3.
- MUST use only fonts defined in section 4.
- MUST NOT stretch, recolor, rotate or add effects to the logo.
- MUST NOT place text on photos without a solid overlay.
- SHOULD use one accent color per layout for shapes, icons and other non-tag fills.
- MAY use several accent colors per layout only in tags and statuses, and MUST NOT exceed 3 different accents per layout; with more categories, use tags on `surface` without color.
- MUST keep one meaning per accent color within a material (same category = same color).
- MUST use `accent-red`, `accent-green` and `accent-orange` only for statuses, never for categories. Category tags use `accent-yellow`, `accent-teal`, `accent-indigo`, `accent-purple`, `accent-pink`.
- MUST keep `primary` dominant: accents MUST NOT take more area in a layout than `primary`.

## 3. Color tokens

<!-- Только HEX и RGB. В колонке «Name» — имя цвета; в 3.4 колонка «Figma» — исходное имя переменной. -->

### 3.1 Brand colors

| Token | Name | HEX | RGB | Use for |
|---|---|---|---|---|
| `primary` | `Niwart Blue` | #1953FF | 25 83 255 | Main brand color: key shapes, text highlights, secondary button border, ghost button text, button hover and pressed fill, focus ring on light backgrounds, input success marker |
| `primary-variant` | `Niwart Neo Blue` | #3A6BFF | 58 107 255 | Blue on dark backgrounds (`bg-dark`) only: shapes, icons, eyebrow text, focus ring |

**Gradient**

<!-- Источник: Figma Branding, node 712:1291 (https://www.figma.com/design/K1KuS3pyAeyVi8kAVHyfb3/Branding?node-id=712-1291).
     CSS: linear-gradient(88deg, #3A6BFF 1.41%, #00C2FF 98.44%) -->

| Token | Name | Type / angle | Stops (HEX, position) | Use for |
|---|---|---|---|---|
| `gradient-neo` | `Neo Gradient` | Linear, 88° | #3A6BFF 1.41% → #00C2FF 98.44% | Restricted — only on `bg-dark`: white logo mark, text highlights, buttons (see 3.5) |

<!-- TBD: `00 - Fundamentals/Dark` #1A1A1A (26 26 26) есть в Figma рядом с `Core/Dark`.
     Подтвердить, нужен ли он, или это остаток старой системы. До решения не использовать. -->

### 3.2 Neutrals

| Token | Name | HEX | RGB | Use for |
|---|---|---|---|---|
| `white` | White | #FFFFFF | 255 255 255 | Main background, cards on `bg-subtle`, text on `primary`, inverse button fill, ghost button hover fill on `bg-subtle` |
| `bg-subtle` | Subtle Background | #F5F7FC | 245 247 252 | Light alternate background: sections, slide and page backgrounds, cards on `white`, inverse button hover fill, ghost button hover fill on `white` |
| `bg-dark` | Dark Background | #05070D | 5 7 13 | Dark alternate background: sections; primary button fill on `white` / `bg-subtle` |
| `surface` | Surface Default | #E7EAF0 | 231 234 240 | Tags |
| `surface-pressed` | Surface Pressed | #D1D5E2 | 209 213 226 | Outlines, pressed state |
| `white-5` | White 5% | #FFFFFF, opacity 5% | 255 255 255 / 0.05 | Hover fill of ghost buttons on `bg-dark` (≈ #121319 on `bg-dark`) |

<!-- `Greys/Surface/Hover` в Figma = #E7EAF0, то же, что Default. Отдельный токен не заводим. -->

**Background variation**

<!-- CSS: linear-gradient(180deg, #FFF 0%, #F5F7FC 20%) -->

| Token | Name | Type / angle | Stops (HEX, position) | Use for |
|---|---|---|---|---|
| `bg-subtle-fade` | Subtle Background Fade | Linear, 180° (top → bottom) | #FFFFFF 0% → #F5F7FC 20% | Variation of `bg-subtle` for a section that directly follows a `white` section (see 3.5) |

### 3.3 Text colors

**On light backgrounds** (`white`, `bg-subtle`)

| Token | Name | HEX | RGB | Use for |
|---|---|---|---|---|
| `text-high` | Text High | #05070D | 5 7 13 | Headlines |
| `text-medium` | Text Medium | #32353D | 50 53 61 | Body text |
| `text-low` | Text Low | #8C91A1 | 140 145 161 | Disabled state, input placeholder (see 3.5); input underline on light backgrounds (~3.1:1) |

**On dark backgrounds** (`bg-dark`)

| Token | Name | HEX | RGB | Use for |
|---|---|---|---|---|
| `text-inverse-high` | Text Inverse High | #FFFFFF | 255 255 255 | Headlines |
| `text-inverse-medium` | Text Inverse Medium | #A3ABC2 | 163 171 194 | Body text |
| `text-inverse-low` | Text Inverse Low | #565E76 | 86 94 118 | Disabled state, input placeholder (see 3.5); border of secondary button and input underline on `bg-dark` (~3.1:1) |

### 3.4 Accents

<!-- Набор из 8 акцентов. Для тегов, статусов и иконок — не как брендовые цвета. -->

| Token | Figma | HEX | RGB | Use for | Text on tag |
|---|---|---|---|---|---|
| `accent-red` | `Accent/Red` | #FF3B30 | 255 59 48 | Negative delta, risk, errors | `text-high` (~5.7:1) |
| `accent-orange` | `Accent/Orange` | #FF9500 | 255 149 0 | Warnings | `text-high` (~9.2:1) |
| `accent-yellow` | `Accent/Yellow` | #FFCC00 | 255 204 0 | Tags | `text-high` (~13.3:1) |
| `accent-green` | `Accent/Green` | #34C759 | 52 199 89 | Positive delta, success | `text-high` (~9.1:1) |
| `accent-teal` | `Accent/Teal` | #5AC8FA | 90 200 250 | Tags | `text-high` (~10.6:1) |
| `accent-indigo` | `Accent/Indigo` | #5856D6 | 88 86 214 | Tags | `text-inverse-high` (~5.7:1) |
| `accent-purple` | `Accent/Purple` | #AF52DE | 175 82 222 | Tags | `text-high` (~4.9:1) |
| `accent-pink` | `Accent/Pink` | #FF2D55 | 255 45 85 | Tags | `text-high` (~5.5:1) |

### 3.5 Color rules

- **Contrast (MUST):** text vs background ≥ 4.5:1 (≥ 3:1 for text ≥ 24 px / 18 pt). Disabled text is exempt. Exceptions: `white` text and icons on `gradient-neo` in button hover and pressed states (≈ 4.4:1 at the start, ≈ 2.1:1 at the end); `gradient-neo` text on `white-5` in ghost button hover and pressed states (≈ 4.2:1 at the start).
- **Approved text/background pairs — light:**
  - `text-high` on `white` / `bg-subtle` / `surface` (~20.1:1 / ~18.8:1 / ~16.7:1)
  - `text-medium` on `white` / `bg-subtle` (~12.3:1 / ~11.4:1)
  - `primary` on `white` / `bg-subtle` (~5.6:1 / ~5.3:1)
- **Approved text/background pairs — dark:**
  - `text-inverse-high` on `bg-dark` (~20.1:1)
  - `text-inverse-medium` on `bg-dark` (~8.8:1)
  - `primary-variant` on `bg-dark` (~4.5:1)
- **Approved text/background pairs — blue:**
  - `white` on `primary` (~5.6:1)
- **Surface (MUST):** text on `surface` MUST be `text-high` only.
- **Gradient (MUST NOT):** `gradient-neo` is restricted — MUST NOT be used anywhere else. Exceptions, all on `bg-dark` only: the mark of the white logo; text highlights (section 4); in buttons (see `ui-kit.md`) — the Primary on dark border, its hover and pressed fill, the Secondary on dark hover and pressed border (button and icon button), Ghost on dark text and Ghost on dark icon button hover icon. Gradient text and icons: ≈ 4.5:1 at the start, ≈ 9.7:1 at the end on `bg-dark`.
- **Subtle fade (MUST):** `bg-subtle-fade` follows all rules of `bg-subtle` (approved text pairs, cards, buttons, inputs). It MUST be used only for an element whose preceding element (directly above) has a `white` background; in any other case use `bg-subtle`.
- **Neo Blue (MUST):** `primary-variant` MUST be used only on `bg-dark` — never on light backgrounds and never as a fill under text. On light backgrounds use `primary`.
- **Disabled (MUST):** `text-low` (~3.1:1 on `white`) and `text-inverse-low` (~3.1:1 on `bg-dark`) MUST be used only for disabled states, never for active text. Exceptions: both as input placeholder text (exempt from the contrast rule; a label is required) and as the input underline; `text-inverse-low` as the border of the secondary button on `bg-dark`.
- **Tag text (MUST):** text on accent tags MUST use the color from the «Text on tag» column in 3.4 (all ≥ 4.5:1).
- **Accents as text (MUST NOT):** accents are for fills, icons and tags, not for running text.

## 4. Typography

| Token | Family | Weights allowed | Use for |
|---|---|---|---|
| `font-heading` | Plus Jakarta Sans | 500 Medium | Headlines, big numbers |
| `font-body` | Plus Jakarta Sans | 400 Regular | Body text, captions, labels |
| `font-accent` | Plus Jakarta Sans | 300 Light Italic | Text highlights |

- **Text highlights (MUST):** highlighted words MUST combine `font-accent` and `primary`; on `bg-dark` — `font-accent` and `gradient-neo` (gradient applied to the text). Neither is used alone for a highlight.
- **Font source:** Google Fonts (license: SIL Open Font License — verify before distribution).
- Add other weights only if confirmed in Figma.
- Type scale, type roles, line heights and fallbacks are defined in each asset file (see section 6).

## 5. Logo

| Version | File | Use on |
|---|---|---|
| Full color | [`assets/logo/niwart-logo-color.svg`](assets/logo/niwart-logo-color.svg) | `white`, `bg-subtle` |
| White | [`assets/logo/niwart-logo-white.svg`](assets/logo/niwart-logo-white.svg) | `bg-dark` |
| Full white | [`assets/logo/niwart-logo-full-white.svg`](assets/logo/niwart-logo-full-white.svg) | `primary` |

- **Clear space:** TBD
- **Minimum size:** TBD

## 6. Asset files registry

| File | Covers | Status |
|---|---|---|
| [`ui-kit.md`](ui-kit.md) | UI kit: type roles, layout grid, tags, buttons, inputs | draft (0.20) |

## 7. Changelog

- 1.0 — 2026-10-13 — Colors and typography imported from Figma Branding (node 622:1633).
- 1.1 — 2026-10-13 — Added `bg-subtle` #F5F7FC as a light background; contrast pairs updated.
- 1.2 — 2026-10-13 — Added `primary-variant` (Niwart Neo Blue) #3A6BFF and `bg-dark` #05070D; dark-background contrast pairs added.
- 1.3 — 2026-10-13 — Neutrals renamed to plain names; text colors moved to 3.3; added `text-inverse-*` for dark backgrounds (values TBD).
- 1.4 — 2026-10-13 — Typography reduced to font families; type roles, rules and fallbacks moved to `ui-kit.md`.
- 1.5 — 2026-10-13 — Sections Spacing, Imagery, Iconography removed; `surface` limited to tags (`text-high` only); `text-low` / `text-inverse-low` set to disabled only; contrast rules in 3.5 recalculated and split by background; `primary-variant` limited to `bg-dark`; `gradient-neo` added as restricted; `font-heading` set to 500 Medium; added `font-accent` and text highlight rule; accents moved from data series to tags; data series rule removed; text colors for accent tags defined; multi-accent rules added to section 2; stale token references fixed.
- 1.6 — 2026-10-13 — Logo files linked; white logo (gradient mark) limited to `bg-dark`; added full white logo for `primary`; `gradient-neo` allowed in the white logo mark.
- 1.7 — 2026-10-14 — `gradient-neo` allowed as button fill on `bg-dark`, with a contrast exception for `white` text and icons; buttons removed from `primary` use and added to `bg-dark` (default fill on light backgrounds); `primary` used for button hover outline.
- 1.8 — 2026-10-14 — `gradient-neo` in buttons changed from fill to border on `bg-dark`; contrast exception for text on gradient removed; `primary` used for secondary button border.
- 1.9 — 2026-10-14 — `primary` used for button hover/pressed fill and focus ring; `primary-variant` for focus ring on `bg-dark`; `gradient-neo` allowed as button fill on hover/pressed on `bg-dark`, with a contrast exception for `white` text and icons.
- 1.10 — 2026-10-14 — Button roles added: `primary` / `primary-variant` for ghost button text, `white` for inverse button fill, `bg-subtle` for inverse hover, `text-inverse-low` allowed as secondary button border on `bg-dark`.
- 1.11 — 2026-10-14 — `white` and `bg-subtle` used as ghost button hover fill (each on the other background).
- 1.12 — 2026-10-14 — `font-accent` changed to 300 Light Italic; text highlights on `bg-dark` use `gradient-neo` instead of `primary-variant`; `gradient-neo` allowed for ghost button text and icon button states on `bg-dark`; added `white-10` (white at 10%) for ghost hover on `bg-dark`; contrast exception for gradient text on `white-10`.
- 1.13 — 2026-10-14 — `gradient-neo` in Secondary on dark changed from icon button hover fill to hover and pressed border (button and icon button).
- 1.14 — 2026-10-14 — `white-10` replaced with `white-5` (white at 5%) for ghost hover on `bg-dark`; contrast exception updated (≈ 4.2:1).
- 1.15 — 2026-10-14 — Input roles: `surface-pressed` for the input underline on light backgrounds; `text-low` / `text-inverse-low` allowed as input placeholder; `text-inverse-low` for the input underline on `bg-dark`.
- 1.16 — 2026-10-14 — Input underline on light backgrounds moved from `surface-pressed` to `bg-subtle`.
- 1.17 — 2026-10-14 — Input underline on light backgrounds moved from `bg-subtle` to `text-low`.
- 1.18 — 2026-10-14 — `primary` used for the input success marker.
- 1.19 — 2026-10-14 — Labels moved from `font-heading` to `font-body` (400 Regular).
- 1.20 — 2026-10-14 — Added `bg-subtle-fade` (linear 180°, #FFFFFF 0% → #F5F7FC 20%): a `bg-subtle` variation allowed only directly after a `white` element; follows all `bg-subtle` rules.
