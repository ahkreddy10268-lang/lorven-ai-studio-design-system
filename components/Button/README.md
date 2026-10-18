# Button

Buttons trigger one action; their label says exactly what happens.

**Markup:** `<button class="l-btn l-btn--primary">Review changes</button>`. Icons go inside as `<span data-icon="export" data-size="16"></span>`.

| Property | Values | Use |
| --- | --- | --- |
| Variant | `--primary` (electric blue fill), `--secondary` (filled neutral, `bg-control`), `--outline` (`border-strong` edge), `--ghost` (no fill until hover), `--tertiary` (link-style, `text-link`), `--destructive`, `--icon` | One primary per view. Secondary for common supporting actions; outline when a supporting action must read as a choice beside a primary; ghost in toolbars and dense rows; tertiary for navigation-like actions ("View source"). Destructive only for irreversible loss. |
| Size | `--sm` (`control-sm` 28px), default (`control-md` 32px), `--lg` (`control-lg` 40px) | `--sm` in toolbars and inside rows; `--lg` in dialogs. |
| Icon | leading, trailing (chevron = navigates elsewhere), icon-only | Icon-only buttons need `aria-label` and a tooltip. |
| Width | default, `--block` | Block only in narrow panels and compact breakpoint dialogs. |
| State | default, hover, pressed, focus, disabled, loading (`aria-busy="true"` + `loading` icon) | Loading keeps the label ("Exporting…") so width does not jump. |

**Keyboard:** Enter/Space activate. Focus ring is `focus-ring`, 2px, offset 2px. Disabled buttons use `aria-disabled="true"` when they must stay focusable to explain why.

**Content:** verb + object, sentence case, ≤ 3 words where possible. Never "OK", "Submit", "Click here".

**Don't:** put two primary buttons side by side; use destructive styling for "Cancel"; use a button for navigation to another page (use a link or tertiary with trailing chevron).
