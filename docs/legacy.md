# Legacy system: retain, rebuild, retire

**Evidence status.** The legacy Figma file ("War Room · QAIG") could not be opened from this work session. Everything below about its contents comes from the inventory supplied in the project brief, not from an audit performed here. Exact token mappings, component properties and whether its theme modes are correctly bound are unknown; they are marked as gaps, not guessed.

## What the brief reports

- Separate Light Colors and Dark Colors sections, 86 colour definitions per mode (layout, content, primary, secondary, success, warning, danger roles).
- Colours: blue `#006FEE`, purple `#7828C8`, green `#17C964`, orange `#F5A524`, pink-red `#F31260`; white light surfaces; pure black dark background.
- Sections for spacing (4px increments), typography, radius (8, 12, 14px) and shadows.
- Earlier Cine Scribe screens (story ideation, beat sheets, oneliners, screenplay, dashboards, responsive, light/dark, some error/success states).
- A HeroUI V3 reference area and other library references; film-reel and clapperboard illustrations.

## Findings that change the recommendation

- **The legacy palette is a component library's default theme, not a brand palette.** The five colours match HeroUI's stock primary, secondary, success, warning and danger. Nothing in the supplied logos uses them.
- **Several fail contrast as used for text or labels** (checked here): green `#17C964` on white 2.2:1, orange `#F5A524` on white 2.0:1, pink-red with white text 4.1:1, purple on black 2.9:1. Only blue clears 4.5:1, barely (4.7:1).
- **Pure black dark mode** gives no room for elevation steps below the canvas, increases halation on light text, and makes black product wordmarks vanish entirely.

## Recommendation

| Legacy foundation | Decision | Why | Where it lives now |
| --- | --- | --- | --- |
| Separate Light and Dark foundations | **Retain** (structure) | Right organising idea | Same semantic names, two modes (`tokens.json`) |
| Role vocabulary (layout, content, primary, secondary, success, warning, danger) | **Retain, re-map** | Roles are sound; names were library-flavoured | `bg-*`, `text-*`, `action-*`, `status-*`; "secondary" becomes a button variant, not a colour |
| 4px spacing increments | **Retain** | Matches the new scale exactly | `space-*` |
| Separate typography, radius, shadow sections | **Retain** (structure) | Good documentation shape | Typography, Spacing, Radius, Shadow sections here |
| State definitions (error, success) | **Retain, extend** | Kept the idea; too few states | Full state model incl. Check/Outdated, generation states |
| 86-colour sets per mode | **Rebuild** | Unknown bindings, library defaults | Three tiers built from the logos; every pair contrast-checked |
| Radius 8 / 12 / 14px | **Rebuild** | Too soft for a precision tool; 14px reads consumer-app | `radius-xs` 2 · `sm` 4 · `md` 6 · `lg` 10 |
| Shadow set | **Rebuild** | Values not supplied | Two shadows only: `shadow-raised`, `shadow-overlay` |
| Typography section | **Rebuild** | Face and scale not supplied | Switzer scale + Courier Prime for screenplay |
| HeroUI component references | **Rebuild** | Third-party patterns, not Lorven's; must not be presented as original | Lorven components on Radix-style behaviour |
| Blue primary `#006FEE` | **Rebuild** | A blue primary is right (and the Lorven Studio direction confirms it); the library value, its white-text contrast (4.7:1) and its pairing with purple are not | Electric blue ramp: `#2563EB` fill (5.2:1 with white), `#60A5FA` links and focus on dark |
| Purple, green, orange, pink-red | **Retire** | Library defaults, contrast failures, no brand basis; purple reads as an AI-product cliché | Status ramps tuned for AA on navy and white; no AI colour |
| Pure-black dark background | **Retire** | No elevation room; halation; logos vanish | Lorven Studio Dark: navy canvas #0B1220 with five lightness steps |
| Earlier product screens as templates | **Retire** | Standing decision: not a visual reference | Workflows inform the IA only |
| Film-reel and clapperboard illustrations | **Retire from UI** | Decorative, unrelated to tasks; licence unknown | Domain icons (`clapper`, `camera`); illustrations only on marketing if their source is confirmed |

## Gaps still open

- Exact legacy token names and values beyond the five colours, and how its modes are bound.
- Which legacy components were customised versus HeroUI defaults.
- Typography face and scale used in the legacy file.
- Origin and licence of the film illustrations.
