# DecisionBand

The decision band is the top of the project overview: the one or two things that need the current person, and the button to act on them.

**Anatomy:** eyebrow (`needs-you` icon + "Needs you · N decisions") · title (`title-2`, the fact) · body (consequence, ≤ 2 lines) · actions (secondary "Later", primary verb) · optional footer row of attention items for other people.

| Variant | Use |
| --- | --- |
| Needs you | Default when at least one decision is assigned to the viewer. `decision-band-bg`, `shadow-raised` in light. |
| Clear (`l-band--clear`) | Nothing needs the viewer: flat, no shadow, one line with the time of the last check. Never hide the band entirely — its absence would read as "still loading". |

**Behaviour:** the primary action opens the dedicated review surface; decisions are never made inside the band. "Later" snoozes until the next change, not forever. Announce changes to the band in a polite live region.

**Don't:** stack multiple bands; add charts or progress meters; list more than three secondary items.
