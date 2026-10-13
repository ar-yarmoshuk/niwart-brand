---
file: ui-kit.md
brand: Niwart
version: 0.1
updated: 2026-10-13
owner: Arty
inherits: 00-core-niwart.md
overrides: none
covers: UI kit (web and product interfaces)
---

# Niwart — UI kit

<!-- Файл ассета. Наследует всё из 00-core-niwart.md.
     Токены цвета и шрифта — только ссылки по имени. Здесь живут размеры, роли и fallback для UI. -->

## 1. Typography

### 1.1 Font families

| Token (core) | Family | Weights | Web font stack |
|---|---|---|---|
| `font-heading` | Plus Jakarta Sans | 500 | `"Plus Jakarta Sans", Arial, sans-serif` |
| `font-body` | Plus Jakarta Sans | 400 | `"Plus Jakarta Sans", Arial, sans-serif` |
| `font-accent` | Plus Jakarta Sans | 500 italic | `"Plus Jakarta Sans", Arial, sans-serif` |

- **Loading:** Google Fonts: 400, 500 and 500 italic only.
- **Fallback:** Arial (Bold for 500, Regular for 400, Italic for 500 italic).

### 1.2 Type roles

<!-- Размеры из Figma (desktop). Роли без значений — заполнить. -->

| Role | Figma style | Font | Weight | Line height | Letter spacing | Desktop |
|---|---|---|---|---|---|---|
| `h5` | `Title/Desktop/H5` | `font-body` | 400 | 1.4 | 0 | 20 / 28 px |
| `label` | `Label/M/Bold` | `font-heading` | 700 | 1.25 | 0 | 16 / 20 px |
| `caption` | `Paragraph/S (caption)` | `font-body` | 400 | 1.67 | 0 | 12 / 20 px |
| `display`, `h1`–`h4`, `body` | TBD | TBD | TBD | TBD | TBD | TBD |

### 1.3 Type rules

- MUST NOT center-align body text. Left-align by default.
- Numbers in tables SHOULD use tabular figures.

## 2. Changelog

- 0.1 — 2026-10-13 — Typography moved from core: font families, web fallback, type roles, type rules.
