Lorven is a working tool for people who make films. It should feel like a well-run production office: calm, exact, and clear about who has to decide what. Craft shows in alignment, typography and restraint — not in glow, gradients or decoration. The look is **Lorven Studio**: deep navy foundations, layered slate surfaces, crisp type and confident electric-blue interaction, with a light theme that is the same system in daylight. One studio, four products (Cine Scribe, Pitch Craft, Cine Sketch, Cine Flow), one system. Lorven is a professional creative studio enhanced by AI — AI makes the work faster and more controllable; it never replaces a good editor with a chatbot.

> Brand colours (`brand-gold`, `brand-gold-deep`, `brand-orange`, `brand-red`, `brand-cyan`) are sampled from the supplied logo files. Interface colours are built beside them, not from them.

## Principles

1. **Creative focus.** The work takes the screen. The deep-navy shell (`bg-shell`) frames a calm workspace; chrome stays out of the canvas, and every action is reachable from the `CommandMenu`.
2. **AI with user control.** AI proposes; people decide. The `PromptComposer` states what will change before it runs, `GenerationStatus` reports only facts the system knows, `OutputReview` keeps current work until a person chooses, and `Provenance` stays on generated work after acceptance.
3. **One ecosystem, distinct workflows.** Every product shares tokens, shell and components; each workspace keeps its own layout — text-first in Cine Scribe, canvas-first in Cine Sketch, slide-first in Pitch Craft, table-first in Cine Flow.
4. **Decisions before decoration.** Every screen answers "what needs me?" first. The `DecisionBand` is the only raised, emphasised panel on the overview. Colour is spent on action (electric blue) and exceptions (status), nowhere else.
5. **Professional-grade reliability.** Approval and currency are different questions — approved work can be Outdated without losing approval. Anything built from something else names its source (`VersionReference`). Replacements come with Undo and History.
6. **Propose, never assume.** Automated matches stay "Proposed · not confirmed" until a person confirms. Never imply guaranteed matching, live sync, verified confidentiality, or features that are not live ("Early access" says so).
7. **Accessible by default.** Every pair of colours is contrast-checked in both themes; status is never colour alone; every control is reachable by keyboard with a visible focus ring.

## Content fundamentals

- **Voice:** a capable first assistant director — plain, specific, unhurried. Lead with the fact, then the consequence: "Screenplay v7 changed 4 scenes. 9 frames were built from v6."
- **Address:** second person ("Needs you", "Your work is safe"). Name people, not roles, when known ("Waiting on Meera").
- **Casing:** sentence case everywhere, including buttons and titles. Uppercase only through the `eyebrow` style and screenplay scene headings.
- **Buttons are verbs + object:** "Review changes", "Confirm match", "Mark as Check". Never "OK", "Submit", "Proceed".
- **Numbers:** numerals always; versions as `v7`; frames as `3.04`; tabular figures (`.l-num`) in lists and tables.
- **Product names** follow the live site and the official lockups: Cine Scribe, Pitch Craft, Cine Sketch, Cine Flow — two words, title case, never abbreviated.
- **Industry words stay industry words:** scene, shot, frame, sequence, revision, coverage. Do not invent synonyms ("moments", "clips").
- **AI copy:** describe what happened and how sure it is ("Matched by scene number and heading"). Name the effect before the action ("Makes 3 new frames. Your current frames stay."). No sparkles, no "magic", no anthropomorphic "I think", no invented percentages or time estimates.
- **No emoji** in the interface.
- **Errors** say what happened, that work is safe, and what to do: "Couldn’t load the change summary. Your work is safe. Nothing was approved or changed."

## Colour

Three layers: primitives (`slate-*`, `blue-*`, status ramps) → semantic tokens (`bg-*`, `text-*`, `border-*`, `action-*`, `status-*`, `shell-*`) → component tokens (`btn-*`, `input-*`, `asset-row-*`, `sidebar-bg`, `composer-bg`, `dialog-*`). Components reference semantic or component tokens only — never primitives or hex.

**Surfaces — dark (Lorven Studio Dark), from back to front:**
`bg-shell` #080F1E (navigation) → `bg-canvas` #0B1220 (app background) → `bg-recessed` / `bg-input` #0D1626 (wells, fields, letterbox) → `bg-surface` #111C2D (working panels) → `bg-raised` / `bg-overlay` #1B2940 (raised panels, menus, dialogs) → `bg-control` #24354D (filled controls) and `bg-hover` → `bg-selected` #192E4D (selection, with `border-selected`). Hierarchy comes from these lightness steps plus `border-default` #2D3C52 — not from shadows or glows. Code and technical content sit on `bg-code` #080F1E.

**Surfaces — light:** the same roles on the same slate ramp read from the top: canvas #F5F7FA, surface and raised #FFFFFF (raised separated by `shadow-raised`), recessed #EDF1F6, ink `text-primary` #0B1220 — the dark theme's canvas colour, so the two themes share one ink. The navy shell stays navy in light mode: the studio frame doesn't change with the lights.

- **Action is electric blue.** `action-primary` #2563EB carries white labels at 5.2:1 in both themes; hover #1D4ED8, pressed #1E40AF. Links and focus use #60A5FA on dark (`text-link`, `focus-ring`) and #1D4ED8 / #2563EB on light. Blue is for primary actions, links, focus, selection, checked controls and the current-item indicator — not for icons, borders or decoration.
- **Cyan belongs to the marks and to information.** `brand-cyan` #00BDFF stays inside the product lockups; the `sky` ramp carries In review and info alerts, so blue never has to mean both "act" and "in review".
- **Warm brand colours (`brand-gold`, `brand-gold-deep`, `brand-orange`, `brand-red`) are for brand surfaces only** — the master logo, cover and marketing. Never for actions or states: gold as an action colour is indistinguishable from the amber `Check` state (see the Directions card).
- **No AI colour.** Generated work is marked by the `aperture` icon and words (`Provenance`), not by violet or gradients.
- **Opacity is not a colour system.** Every text, border and fill is a solid token; translucency appears only in `scrim` and shadows.
- **Recommended default theme per product:** Cine Sketch and Pitch Craft dark (artwork and slides judged against a neutral dark); Cine Scribe light for long reading, with dark available; Cine Flow follows the user. A user's explicit choice always wins and persists.

## Status model

| Family | Question | Values | Form |
| --- | --- | --- | --- |
| Approval | Who signed off? | Draft · In review (sky) · Approved · Changes requested | Filled chip (`status-*-bg` + `status-*-fg`) with icon |
| Currency | Does it still match its source? | Current · Check · Outdated | Outlined chip (`status-check-border`, `status-outdated-border`) with link-family icon |
| Attention | What does it ask of me? | Needs you · Waiting on *name* · No action needed | No container; weight + icon only (`text-primary` 600 for Needs you) |

- Order in a row is always Approval → Currency → Attention.
- Every status shows a word and an icon. Colour is the third cue, never the only one.
- `Current` is quiet (`text-muted`); show it only where its absence would be ambiguous (e.g. tables). In lists, omit Current.
- `Check` means the source changed in a way that *may* affect this asset. `Outdated` means the source has moved on and this asset no longer reflects it.
- Changing currency never changes approval. Review surfaces say so in their footer.

## Typography

- **Interface: Switzer** (`--font-sans`, variable 100–900 upright and italic from `fonts/`), falling back to Helvetica Neue / Arial. Licensed under the Fontshare Free Font EULA (Indian Type Foundry, in the brand folder): commercial use in web and apps is permitted, but the font files may not be redistributed, passed to outside agencies or developers, or self-served as web fonts without ITF's written consent. Ship the web product through Fontshare's own font API, and have every designer or developer download Switzer from fontshare.com themselves. Switzer was chosen over Inter (ubiquitous; reads as a template default) and Geist (excellent and OFL-licensed, but strongly associated with Vercel's identity): it is already in the brand folder, has enough character in its *a*, *t* and numerals, and stays tight in dense production tables. If the product must self-host fonts and ITF consent is not given, switch `--font-sans` to Geist — the scale below holds without changes. Use `display` once per screen (project title), `title-1` for page titles, `title-2` for sections and dialogs, `title-3` for asset names, `body` (14/20) as the default, `label` for controls, `caption` for metadata (never below 12px), `eyebrow` for one product label per view.
- **Technical: Geist Mono** (`--font-mono`, OFL, Google Fonts) only in `TechnicalBlock` — shot data, settings, IDs.
- **AI-generated text** is set exactly like human text (same face, size and colour); `Provenance` marks it. No italics, tints or gradients for AI output.
- **Screenplay: Courier Prime** (`--font-script`) for scene headings (`scene-heading`, uppercase, bold) and action/dialogue excerpts (`script-body`). Writers read Courier as "the script"; it also signals at a glance that text is quoted source, not UI copy. Load from Google Fonts where excerpts appear.
- **Brand: Nexa** (`--font-brand`) ships with the brand files. Keep it to brand surfaces (studio shell, cover, marketing) until its role and licence are confirmed; never in product UI.
- Numbers in lists and tables use tabular figures (`.l-num`).
- Measure: body copy ≤ 64ch.

## Spacing, layout and shape

- 4px base: `space-1` 4 · `space-2` 8 · `space-3` 12 · `space-4` 16 · `space-6` 24 · `space-8` 32 · `space-10` 40.
- Controls: `control-sm` 28px (toolbars, dense tables), `control-md` 32px (default), `control-lg` 40px (dialogs). Pointer targets never below `target-min` 24px.
- Rows: `row-min` 56px; padding `space-3`/`space-4`.
- Radius hierarchy: `radius-xs` 4px (thumbnails, kbd), `radius-sm` 6px (chips, nav and menu items, segments), `radius-md` 8px (buttons, inputs, selects), `radius-lg` 12px (cards, panels, menus, composer), `radius-xl` 16px (dialogs, command menu, large workspace containers), `radius-full` (avatars, switches, count badges). Adjacent elements step down one level inside their container (a 12px panel holds 8px controls). Navigation items are rounded rectangles, never capsules.
- **Breakpoints:** compact `< bp-medium` (720px) — single column, asset status wraps under the title, review stacks source above match; medium `≥ 720px` — two-column overview, metadata inline; wide `≥ bp-wide` (1200px) — overview gains an activity column, review shows source and match side by side. Gutters `space-5` / `space-6` / `space-8`.
- Elevation: surfaces step lighter as they come forward (dark) or sit on white with `shadow-raised` (light); `shadow-overlay` only on menus, popovers and dialogs. No glows, blur or glass.

## Motion

- Durations: 120ms for hover/press colour, 200ms for menus and popovers, 280ms for dialogs and panel transitions. Easing `cubic-bezier(.2,0,0,1)` in, `cubic-bezier(.4,0,1,1)` out.
- Motion explains state change (a row moving from "Needs you" to resolved), never decorates.
- Respect `prefers-reduced-motion`: spinners stop, skeletons stop pulsing, transitions become instant.

## Interaction states

- **Focus:** 2px solid `focus-ring` with 2px offset on every focusable element, in both themes (≥ 3:1 on every surface).
- **Hover:** `bg-hover` on rows, menu items, ghost and icon buttons; `bg-control-hover` on secondary buttons; primary darkens one step (`action-primary-hover`).
- **Controls:** `bg-control` sits one step beyond `bg-hover`, so a secondary button stays visible inside a hovered row. Labels on controls are `text-primary` or `text-secondary`, never `text-muted`; on `bg-control-hover` always `text-primary`.
- **Fields:** at rest a `border-strong` edge on `bg-input`; blue appears only on focus (`border-selected` + `focus-ring`) or when invalid (`status-error-fg`). No permanently blue outlines.
- **Selected:** `bg-selected` plus a 2px `border-selected` inside edge — never fill alone.
- **Disabled:** `text-disabled` on `bg-control` (buttons) or a dashed `border-subtle` edge (fields) — never brighter than the enabled state; `aria-disabled`, not-allowed cursor; explain *why* nearby when it isn't obvious.
- **Loading:** skeletons (`skeleton`) shaped like the content; buttons keep their label and add a spinning `loading` icon with `aria-busy`.

## Iconography

- An original Lorven set: 58 icons on a 24×24 grid, 2px padding (20px live area), 1.5px stroke (`icon-stroke`), round caps and joins, `currentColor`. Sizes `icon-sm` 16, `icon-md` 20, `icon-lg` 24; empty states may use 32.
- Outline is the default. Fill appears only as meaning inside a status glyph (`in-review` half fill, `needs-you` centre dot) — never as a selected-state variant.
- Status icons belong to families: approval uses circles, currency uses links and a diamond, attention uses target/hourglass/dash. Don't borrow across families.
- Product icons (`product-cine-scribe`, `product-pitchcraft`, `product-cinesketch`, `product-cineflow`) are for tight spaces inside the UI (tabs, inline mentions). They never replace the official product marks on brand surfaces, switchers or headers.
- AI generation uses `aperture` — a camera iris — never a sparkle. It is the one AI glyph, used on Generate buttons and on `Provenance`. Everything else is named by what it does (`frame` for a proposed match, `compare`, `regenerate`, `stop`, `history`).
- Generic utility glyphs may come from Lucide in code only when a Lorven icon doesn't exist, set to `strokeWidth={1.5}` so weights match; add a Lorven icon when one is used more than twice.
- In code: load `components/bundle.js`, then `<span data-icon="approved" data-size="16"></span>` or `Lorven.icon("approved", 16, "Approved")`. As files: the **Icons** asset group (ink `#1b1a18`; recolour by editing `stroke`).

## Logos

The **Logos** asset group holds the official files. Never redraw, recolour, crop, outline or re-typeset them.

- **Master — Lorven AI Studio:** geometric wordmark, gold-gradient E, orange-to-red STUDIO. Use `lorven-studio-colour.png` on light grounds, `lorven-studio-white.png` on dark grounds (keeps the gold E and red STUDIO), `lorven-studio-black.png` for single-ink and print. Clear space: at least the height of the E on every side.
- **Products — Cine Scribe, Pitch Craft, Cine Sketch, Cine Flow:** film strip + two-line wordmark in black + `brand-cyan` disc with the product symbol. There is no reversed version: on dark surfaces place the lockup on a white plate (`.l-lockup`: `slate-0`, `radius-sm`, 4px × 6px padding). Minimum height 30px; below that the two-line wordmark stops being legible.
- **In the shell** use the white master, cropped to its transparent margin only (see `AppSidebar`).
- **In product UI** the product lockup appears only where the product itself is the subject (switcher, onboarding, empty product states). Navigation and breadcrumbs name the product in text. Small product glyphs inside the UI use the `product-*` icons, which complement and never replace the marks.
- **Don't** use the product SVGs from this system's asset store: the store strips their `<style>` blocks, so they render black. The original SVGs are sound except that each wordmark is live text in Riosark, which falls back to a serif wherever that font isn't installed. Use the PNGs until SVGs are re-exported with outlined wordmarks and presentation attributes.

## Components

- **Shell:** `AppSidebar`, `CommandMenu`, `Inspector`, `ContextBar`, `ProductSwitcher`
- **Actions and inputs:** `Button` (primary, secondary, outline, ghost, link, destructive, icon), `TextField`, `SelectionControls`, `Select`
- **Navigation:** `Tabs`, `SegmentedControl`
- **AI:** `PromptComposer`, `GenerationStatus`, `OutputReview`, `Provenance`
- **Creative workspace:** `StoryboardFrame`, `SceneCard`, `ChangeReview`
- **Content and workflow:** `AssetRow`, `VersionReference`, `TechnicalBlock`, `StatusChip`, `DecisionBand`, `ConfirmDialog`
- **Feedback:** `States`, `Alert`, `Badge`, `ToastTooltip`
- **Foundations pages:** `Icons`, `Directions`

Load `components/bundle.css` for styles and `components/bundle.js` for icons; markup, states and keyboard behaviour are in each component's guidelines. Behaviour (focus traps, menus, listboxes) follows Radix primitives in code; Lorven owns the visual layer.

## Using the system

1. Start from a semantic token; add a component token only when a component needs a decision that differs from the semantic default.
2. One primary action per view. Secondary actions are `l-btn--secondary`; navigation-like actions are `l-btn--tertiary`.
3. Put decisions on the dedicated review surface; the overview only summarises and links (progressive disclosure).
4. Check every new screen in both themes with long titles, dense lists, artwork thumbnails and all three status families present.
