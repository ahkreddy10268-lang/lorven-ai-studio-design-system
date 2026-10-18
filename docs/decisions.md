# Accessibility and open decisions

## Accessibility review

Contrast was computed for every text, border, focus and status pair in both themes (WCAG 2 relative luminance). All pass:

| Pair | Light | Dark | Minimum |
| --- | --- | --- | --- |
| `text-primary` on `bg-surface` | 18.7 | 15.9 | 4.5 |
| `text-muted` on `bg-hover` (lowest text pair) | 5.1 | 4.8 | 4.5 |
| `text-muted` on `bg-selected` | 5.3 | 5.3 | 4.5 |
| `text-on-action` on `action-primary` | 5.2 | 5.2 | 4.5 |
| `status-check-fg` on `bg-surface` | 7.1 | 9.7 | 4.5 |
| `border-strong` on `bg-raised` (control edges, lowest) | 3.4 | 3.1 | 3.0 |
| `focus-ring` on `bg-raised` | 5.2 | 5.7 | 3.0 |

Also checked: every approval chip's label on its own fill (≥ 4.5 both themes), currency outlines on surfaces (≥ 3), `border-selected` on `bg-selected` (≥ 3), `focus-ring` on `bg-recessed` and `bg-selected` (≥ 3).

**Known limitations**
- `text-disabled` intentionally falls below 4.5:1 (permitted for inactive components). Disabled controls must have a reason visible nearby.
- Approved (green) and Changes requested (orange) are close in lightness; they rely on different words and icons, not colour. Do not show either as a bare colour dot.
- `border-strong` on `bg-raised` in dark mode is 3.1:1 — compliant with little margin; place inputs on surface or input wells, not on raised panels, where possible.
- Focus order, screen-reader announcements and keyboard flows are specified in component guidelines but have not been tested with assistive technology.
- Product lockups at 30px are recognisable but their wordmarks are near the legibility floor; a symbol-only asset is needed for smaller uses.

## Open decisions

| # | Decision | Owner | Blocks |
| --- | --- | --- | --- |
| 1 | Re-export the four product logos with outlined wordmarks and presentation attributes (survives `<style>` stripping), add a disc-only mark for sizes under 30px, and confirm which Cine Sketch export is final. Outlining needs the Riosark licence confirmed | Brand owner | Crisp marks, small sizes |
| 2 | Switzer EULA reviewed: commercial web/app use allowed; redistribution, hand-off to external developers and self-hosted font serving need ITF consent. Decide: Fontshare API delivery, or request consent for self-hosting. Also: keep this system private, or remove the font files before sharing it outside the team. The unnamed "behance" font has no licence on file — not used. | Product + legal | Shipping Switzer, sharing this system |
| 3 | Approve a reversed (white) product lockup, or confirm the white plate as the permanent dark-mode rule | Brand owner | Dark-mode switcher |
| 3b | What is Nexa's role — the master wordmark's face, or a brand display face? | Brand owner | `--font-brand` |
| 4 | Replace placeholder Salt Orchard content with the established sample (characters, scenes, people) | Design | Pilot materials |
| 5 | How scene matches are produced and what confidence can honestly be shown | Engineering | `ChangeReview` copy |
| 6 | Who may mark Check/Outdated as resolved, and does resolving require re-approval? | Product | Workflow rules |
| 7 | Default theme per product vs. one global setting | Product (pilot) | Settings |
| 8 | Data tables and charts — not designed; add only when a real Cine Flow view needs them | Design | Cine Flow scheduling |
| 9 | Confirm product name spelling (two words, per site and lockups) across product, marketing and the V2 brief | Brand owner | Copy everywhere |
| 10 | Representative full screens (overview, review, Cine Sketch workspace) are held until the usability pilot runs; confirm whether that decision still stands | Reddy | Screen deliverables |
| 11 | Confirm the stack (framework, UI library, styling) before implementing the shadcn mapping in *Implementation and governance* | Engineering | Build |
| 12 | Which generation settings the product really supports (variations, aspect ratio, style references) — the composer shows only those | Product + engineering | `PromptComposer` |

## Technical dependencies

- **Tokens:** `tokens.json` (three tiers; aliases resolve per theme) compiles to CSS custom properties with `[data-theme="light"]` and `[data-theme="dark"]` blocks. Switching the attribute switches every component.
- **Native design-tool variables:** not created in Figma from this session (the connector was unavailable). An import-ready export is provided as three collections — *Primitives*, *Semantic* (Light, Dark), *Component* — in W3C token JSON, with aliases preserved.
- **Icons:** one sprite in `components/bundle.js` (`Lorven.icon`, `data-icon`); individual SVGs in the Icons asset group.
- **Fonts:** Switzer from `fonts/` (as declared on the page); Courier Prime and Geist Mono from Google Fonts.
