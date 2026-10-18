# TextField

Text fields collect short text, search terms and notes, always with a visible label.

**Markup:** `<label class="l-field"><span class="l-field__label">Scene title</span><span class="l-input"><input></span><span class="l-field__help">…</span></label>`. Search adds a leading `search` icon and optional `.l-kbd` shortcut hint. Multi-line uses `l-input--area` with a `textarea`.

| State | Treatment |
| --- | --- |
| Default / hover | `input-border` → `text-secondary` border on hover |
| Focus | `border-selected` + 2px `focus-ring` |
| Filled | value in `text-primary` |
| Invalid | `is-invalid`, `input-border-invalid`, `aria-invalid="true"`, error message with `error` icon linked by `aria-describedby` |
| Read-only | `is-readonly`: `bg-recessed`, no border, optional `lock` icon; still selectable and copyable |
| Disabled | `is-disabled`: `bg-hover`, `text-disabled`; prefer read-only when the value matters |

**Content:** labels are nouns ("Shot number"). Mark the minority case: if most fields are required, label optional ones "(optional)". Validation says how to fix it: "Use a number and optional letter, like 12A." Validate on blur, not per keystroke.

**Don't:** use placeholder text as the label; show an error before the user has left the field.
