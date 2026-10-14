# Niwart — Brand system

Brand guidelines for Niwart in a machine-readable format: tokens and rules that people and AI tools (Claude) use to create brand materials.

## Files

| File | What it is |
|---|---|
| [`00-core-niwart.md`](00-core-niwart.md) | Core — single source of truth: colors, text colors, accents, contrast rules, typography, logo. |
| [`ui-kit.md`](ui-kit.md) | UI kit — type roles, layout grid, tags, buttons and inputs for web and product interfaces. |
| [`assets/logo/`](assets/logo/) | Logo files: full color, white (gradient mark), full white. |

## How it works

- `00-core-niwart.md` holds only what is shared by all materials.
- Each asset file (UI kit, deck, social media…) inherits from core and adds its own sizes, grids and components.
- Asset files reference tokens by name (`primary`, `font-heading`, `text-high`), never by raw value.
- Rules use MUST / SHOULD / MAY. If an asset file conflicts with core and declares no override, core wins.

## Using with Claude

Add `00-core-niwart.md` and the relevant asset file to a Claude Project (Project knowledge) or reference them in `CLAUDE.md`, and ask Claude to follow them when creating materials.

## Source

Figma — Branding: [node 622:1633](https://www.figma.com/design/K1KuS3pyAeyVi8kAVHyfb3/Branding?node-id=622-1633), gradient — [node 712:1291](https://www.figma.com/design/K1KuS3pyAeyVi8kAVHyfb3/Branding?node-id=712-1291).
