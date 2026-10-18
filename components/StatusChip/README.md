# StatusChip

Status chips tell people where an asset stands, in three separate families that are never merged.

| Family | Classes | Values |
| --- | --- | --- |
| Approval (filled) | `l-chip--draft`, `--review`, `--approved`, `--changes` | Draft, In review, Approved, Changes requested |
| Currency (outlined) | `l-chip--current`, `--check`, `--outdated` | Current, Check, Outdated |
| Attention (uncontained) | `l-attn--needs`, `l-attn`, `l-attn--none` | Needs you, Waiting on *name*, No action needed |

**Markup:** `<span class="l-chip l-chip--check"><span data-icon="check-source" data-size="16"></span>Check</span>`. Use the icon that belongs to the value: draft, in-review, approved, changes-requested, current, check-source, outdated, needs-you, waiting, no-action.

**Size:** regular 22px high; `l-chip--compact` 18px for context bars and dialog lists only.

**Rules**
- Order: Approval → Currency → Attention.
- Always word + icon. Never a colour dot alone.
- Chips are not buttons. If a status is actionable, put a button or link next to it.
- Omit `Current` in lists; show it in tables where an empty cell would be ambiguous.
- Waiting names a person when known ("Waiting on Meera"), otherwise a role.

**Don't:** recolour a chip for emphasis; invent new statuses; show "Approved" green to mean "up to date".
