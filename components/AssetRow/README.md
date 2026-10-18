# AssetRow

Asset rows list a project's work — scripts, decks, boards, shot lists — with enough status to decide where to go next.

**Anatomy:** thumbnail (56×32, letterboxed in `bg-recessed`; an icon when there is no artwork) · title (`title-3` weight, truncates) · metadata (version, product, source link, person, time) · status cluster (approval, currency, attention; or one action).

| Property | Values |
| --- | --- |
| State | normal, hover (`bg-hover`), selected (`asset-row-selected-bg` + 2px `border-selected` edge), recently changed (`l-asset__changed` mark + word "Changed"), unavailable (`is-unavailable`, dashed thumbnail, reason, "Request access") |
| Density | default (`row-min` 56px). A compact table view belongs to a future data-table component, not a row variant. |

**Adaptive list:** the list sorts by attention first (Needs you, then changed, then the rest). At compact widths the status cluster wraps beneath the title; nothing is hidden.

**Keyboard:** the list is a `listbox` (single selection) or a plain list of links; Up/Down move, Enter opens. Source links inside metadata are separate tab stops.

**Content:** metadata ordered version → product → source → person/time. "Built from Screenplay v6" always links to that version.

**Don't:** put more than one action button in a row; use cards for this list (rows scan faster and align status columns).
