# Lorven AI Studio — Design System (download package)

Open `index.html` in a browser to browse every component, icon and document. The theme button flips light and dark.

## What is inside
| Folder | Contents |
| --- | --- |
| `tokens/tokens.css` | All tokens as CSS custom properties. Three tiers (primitives → semantic → component). Set `data-theme="light"` or `"dark"` on `<html>`. |
| `tokens/*.tokens.json` | W3C design-token JSON for Figma / Tokens Studio: Primitives (151), Semantic.Light (56), Semantic.Dark (56), Component (24). Import order and steps: `tokens/FIGMA-IMPORT.txt`. |
| `tokens/lorven-tokens.catalogue.json` | Full catalogue with usage notes per token. |
| `tokens/fonts.css` | Switzer via Fontshare's API, Geist / Geist Mono / Courier Prime via Google Fonts. |
| `components/` | 31 working previews (`<Name>/preview.html`, both themes) with usage guidelines (`<Name>/README.md`), plus `bundle.css` and `bundle.js` (icon sprite). |
| `icons/` | 58 original icons as individual SVGs (24px grid, 1.5px stroke, `currentColor`). |
| `docs/` | Research, decisions and accessibility review, governance and decision log, legacy retain/rebuild/retire, Lorven Studio refinement. |
| `README.md` | The brand book. |

## Not included, on purpose
- **Switzer font files.** The Fontshare licence forbids redistribution and hand-off to outside developers. Load it through `fonts.css`, or use Geist.
- **Logo files** (your supplied master and product lockups). Use your originals. The product SVGs need re-exporting with outlined wordmarks (see `docs/decisions.md`, item 1).

## Status
Concept-stage. Not tested in an application, not imported into Figma, no usability pilot run, no assistive-technology testing. See `docs/decisions.md` for open decisions.
