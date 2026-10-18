# Lorven Studio refinement

The October refinement evolved the existing system toward the Lorven Studio direction (six visual references: navy settings and documentation screens, navigation and tab-bar studies, a dark form-control kit, and a proposed dark palette). The references were treated as one direction, not six styles; their branding, content, photography and presentation frames were not reused.

## Audit of the existing system

| Area | Finding | Action |
| --- | --- | --- |
| Token architecture (primitive → semantic → component, two themes on one name set) | Sound; components already referenced only semantic/component tokens | **Preserved** — the refinement changed values, not structure |
| Warm-graphite neutrals | Conflicted with the navy direction; a warm light theme beside a cool dark theme would read as two products | **Replaced** by one navy-slate ramp used from the top (light) and the bottom (dark) |
| `cine` action ramp on the logo hue | Too quiet for the confident interaction the references show | **Replaced** by electric blue; cyan kept for marks and info |
| Status model (approval / currency / attention) | Correct and differentiating | **Preserved**; In review moved to sky so blue only means act/selected |
| Brand colours sampled from logos | Correct | **Preserved**, brand surfaces only |
| Radii 2/4/6/10 | Tighter than the direction | **Improved** to 4/6/8/12/16 by container level |
| Button variants (primary, secondary-as-outline, tertiary, destructive, icon) | Missing a filled secondary and a ghost | **Improved**: primary, secondary (filled), outline, ghost, link, destructive, icon |
| Inputs on `bg-surface` | Fields read like cards on dark | **Improved**: `bg-input` well, blue only on focus or error; disabled is quieter than enabled |
| Charcoal shell | Right idea | **Consolidated** into the navy shell, with nested sub-navigation and count badges |
| Feedback set (states, toast) | No inline alerts, no badges | **Added** `Alert`, `Badge` |
| Technical content | Not covered | **Added** `TechnicalBlock` (Geist Mono on `bg-code`) |
| Typography (Switzer, Courier Prime) | Working | **Preserved**; Geist Mono added for technical data only |
| Icons (58, 1.5px) | Working | **Preserved**; Lucide only as a matched fallback |
| Hard-coded values | Two literals (`graphite-0` in switch and plate) | **Removed** — now `slate-0` |

## Proposed palette, validated

| Proposed | Result | Shipped |
| --- | --- | --- |
| background #0B1220, sidebar #080F1E, surface #111C2D, raised #1B2940, hover #24354D, selected #192E4D, border #2D3C52 | Steps are visible; text passes on all | **As proposed** |
| text-primary #F4F7FB, text-secondary #AAB7C9 | 11.6–17.8:1 and 6.1–9.4:1 | **As proposed** |
| text-muted #8492A6 | 3.9:1 on hover rows — fails | **#94A3B8** (4.8:1 lowest) |
| border-strong #40516A | 2.1:1 on surface — fails for control edges | **#63748E** (3.1:1 lowest) |
| primary #3B82F6 with white label | 3.68:1 — fails | **#2563EB** fill (5.17:1); #3B82F6 kept in the ramp |
| primary-hover #2563EB | Would be the new default | **#1D4ED8** hover, **#1E40AF** pressed |
| focus-ring #60A5FA | 5.7–6.7:1 on dark surfaces | **As proposed** (dark); #2563EB on light |
| primary-subtle #152D55 | Works | **As proposed** (`action-primary-subtle`) |
| violet #8B5CF6 (optional AI accent) | 4.2:1 with white; competes with blue | **Not adopted** — `aperture` + `Provenance` instead |

## Light theme

Kept as a first-class theme on the same semantic names. Values changed only where the shift to one cool ramp required it: canvas #F5F7FA, ink #0B1220 (the dark canvas colour), muted #56677F, borders on the slate ramp. Every pair was re-checked; all pass.

## Token-file audit (W3C export)

An independent validator read the four exported files only (not the generator), resolved every alias and checked contrast on the resolved values.

**Already correct:** every semantic alias resolves to a primitive; every component alias resolves through the semantic layer; no dangling or circular references; Light and Dark have identical names (56 each); every text, link, button-label, input-edge, focus, selection, status and shell pair passes WCAG 2.2 AA in both modes.

| Finding | Why it mattered | Fix (smallest change) |
| --- | --- | --- |
| `scrim` stored as `rgba()` text | The only non-hex colour; a variable import rejects it, so dialog backdrops would not import | Two 8-digit-hex primitives (`scrim.light`, `scrim.dark`); `scrim` now aliases them |
| Light: recessed, hover, control and code all `#EDF1F6` | Hover invisible on recessed areas; secondary buttons 1.06:1 against the canvas; a secondary button disappeared inside a hovered row | Light hover → `slate.150`, control → `slate.200`, control-hover → new `slate.250` (control vs canvas now 1.28:1) |
| Dark: hover and control both `#24354D` | Same disappearing-button case | Dark control → `slate.700`, control-hover → `slate.650` |
| Switch painted with a border token and a raw primitive; logo plate a raw primitive | Bypassed the semantic layer | New semantic `bg.plate`; component tokens `switch.track-off`, `switch.track-on`, `switch.thumb`, `lockup.plate` |
| Typography, motion, breakpoints, z-index missing from the files | Figma variables could not carry the type scale or motion | Added to Primitives (numbers and strings); shadows documented as effect styles |
| Switches rendered as broken checkboxes (CSS) | `.l-check input` out-ranked `.l-switch` | Checkbox rules scoped to `:not(.l-switch)` |

**Accepted duplicates (intentional):** light surface = raised = overlay = input = plate (white; raised and overlay are separated by shadow and border); dark raised = overlay; dark recessed = input; dark code = shell. None of these overlap interactively.

**Rules made explicit instead of weakening values:** `text-muted` is never placed on `bg-control` (4.2–4.4:1); labels on `bg-control-hover` are `text-primary`.
