# Implementation and governance

## Technical foundation (recommended, not yet implemented)

No Lorven codebase was available, so nothing here has been built or tested in the application. The recommendation assumes a React + Tailwind front end; confirm the actual stack first and adapt rather than migrate.

- **Behaviour:** shadcn/ui components on Radix primitives — code-owned, accessible by default, and themable through CSS variables. Use one primitive family throughout; do not mix Radix and another headless library.
- **Visual layer:** Lorven's own. Restyle every shadcn component with Lorven tokens; never ship its default look.
- **Tokens:** CSS custom properties from `tokens.json`, switched by `[data-theme="light" | "dark"]` on `<html>`; Tailwind `@theme` maps utilities to the same variables.
- **Icons:** the Lorven sprite (`Lorven.icon`); Lucide only for missing generic glyphs at `strokeWidth={1.5}`.
- **Fonts:** Switzer through Fontshare's API (licence), Courier Prime (OFL) self-hosted or Google Fonts; Geist as the drop-in if self-hosting Switzer is not permitted.
- **Docs:** extend Storybook if the codebase already has it; otherwise this design system is the reference until component count justifies one.

### shadcn variable mapping

| shadcn variable | Lorven token |
| --- | --- |
| `--background` | `bg-canvas` |
| `--foreground` | `text-primary` |
| `--card` / `--card-foreground` | `bg-surface` / `text-primary` |
| `--popover` / `--popover-foreground` | `bg-overlay` / `text-primary` |
| `--primary` / `--primary-foreground` | `action-primary` / `text-on-action` |
| `--secondary` / `--secondary-foreground` | `bg-hover` / `text-primary` |
| `--muted` / `--muted-foreground` | `bg-recessed` / `text-muted` |
| `--accent` / `--accent-foreground` | `bg-selected` / `text-primary` |
| `--destructive` | `action-destructive` |
| `--border` / `--input` | `border-default` / `border-strong` |
| `--ring` | `focus-ring` |
| `--sidebar` and `--sidebar-*` | `bg-shell`, `shell-text`, `shell-selected`, `shell-indicator`, `shell-border` |
| `--radius` | `radius-sm` (4px) |

Lorven status tokens (`status-*`) have no shadcn equivalent; expose them as Tailwind colours.

## Rules for tokens

1. Components reference semantic or component tokens, never primitives or hex.
2. A new semantic token needs a role no existing token covers, values for both themes, a usage note naming its grounds, and a passing contrast check in both themes.
3. A component token exists only when the component must differ from the semantic default; it aliases a semantic token.
4. Product-specific tokens (layer 4) are allowed when a workspace has a real need — e.g. a script page colour in Cine Scribe — and must alias semantic tokens.
5. Never rename a token in place; add the new one, migrate, then retire the old one in a noted release.

## Adding or changing a component

1. Check the inventory: extend a variant before adding a component.
2. Write the guideline first: purpose, anatomy, properties, states, keyboard, content, and when not to use it.
3. Build the preview in both themes with real Lorven content, long strings and every state.
4. Contrast-check any new colour pair; test keyboard and screen-reader behaviour.
5. Record the decision below.

## Accessibility checklist (WCAG 2.2 AA)

- Text ≥ 4.5:1 (≥ 3:1 at 24px or 19px bold); control borders, icons and focus rings ≥ 3:1 — in both themes.
- Status never by colour alone: word + icon.
- Every control reachable by keyboard; visible `focus-ring`; logical order; no traps outside modals.
- Dialogs and menus manage focus and restore it on close.
- Targets ≥ 24px (`target-min`).
- Form errors named in text, linked with `aria-describedby`, validated on blur.
- Live regions for generation status (`status`) and failures (`alert`).
- `prefers-reduced-motion` stops spinners, pulses and transitions.
- Disabled controls explain why nearby.

## Decision log

| Date | Decision | Reason | Trade-off |
| --- | --- | --- | --- |
| 2026-10-17 | Direction B (precision workspace) for product UI; warm brand on brand surfaces | Gold as action is indistinguishable from the amber Check state | Product UI is cooler than the master brand |
| 2026-10-17 | Action ramp on the product-disc hue (198°) — superseded the same day by electric blue | — | — |
| 2026-10-17 | Three status families with three forms | Approval and currency must not be confused | More visual vocabulary to learn |
| 2026-10-17 | Switzer interface, Courier Prime screenplay, Geist as licensed fallback | Brand-supplied, distinctive; Inter reads as a template | Switzer licence limits self-hosting |
| 2026-10-17 | Studio shell dark in both themes (charcoal, then navy #080F1E) | Frames the canvas; carries the white master logo | Shell needs its own small token set |
| 2026-10-17 | Proposed accent `#C65D40` not adopted | White text 4.17:1 (fails); 1.26:1 against Changes requested | No terracotta accent in UI |
| 2026-10-17 | Legacy HeroUI palette and pure-black dark retired | Library defaults, contrast failures, no brand basis | Existing screens must be re-themed |
| 2026-10-17 | `aperture` replaces sparkle as the AI glyph | Ownable, film-native, no implied magic | Needs teaching once; always paired with a word |
| 2026-10-17 | Product names written as two words | Matches the live site and the official lockups | Differs from the V2 brief spelling |
| 2026-10-17 | **Lorven Studio refinement:** navy-slate neutrals replace warm graphite in both themes; electric blue replaces the cine ramp | Direction set from six visual references; one cool ramp keeps light and dark one system | Warm brand now lives only in logos and brand surfaces |
| 2026-10-17 | Primary fill `#2563EB`, not the proposed `#3B82F6` | White label on `#3B82F6` is 3.68:1 (fails AA); `#2563EB` is 5.17:1 | Slightly deeper blue; `#3B82F6`/`#60A5FA` kept for links and focus on dark |
| 2026-10-17 | Proposed `border-strong` `#40516A` → `#63748E`; muted text `#8492A6` → `#94A3B8` | Control edges were 2.1:1 (need 3:1); muted text 3.9:1 on hover rows | Borders read a little stronger than the references |
| 2026-10-17 | Optional violet AI accent declined | AI is marked by `aperture` + words; violet competes with blue, fails with white text (4.2:1) and reads as an AI cliché | One fewer accent to express "AI" |
| 2026-10-17 | In review moves from blue to sky | Blue now means act/selected; review is a state | Sky sits close to brand cyan, used only in chips and info |
| 2026-10-17 | Radius hierarchy 4 / 6 / 8 / 12 / 16 | Brief's guidance; softer than before but still stepped by container | Less "precision tool", more contemporary |
| 2026-10-17 | Token-file audit: hex scrim, separated hover/control fills, switch and plate tokens, typography and motion added to the variable export | Import failure, invisible controls and layer bypasses found by an independent validator | One extra slate step (250); four new component tokens |
| 2026-10-17 | No full screens until the usability pilot runs | Standing project decision | Components are proven in isolation only |
