# OutputReview

Output review is where generated options are compared with the current work and a person decides what to keep.

**Anatomy:** header (target and prompt excerpt, Generate again) · current work on the left · options A–C with provenance overlay and actions (Use this, Edit, Discard) · footer stating the consequence and the safety net, with Keep current.

**Behaviour:** choosing replaces the current item and shows a toast with Undo; the replaced version stays in History. Arrow keys move between options, Enter chooses, Delete discards. Discarded options are gone only when the review closes.

**Don't:** pre-select an option on the user's behalf; allow "Use all" when it would overwrite reviewed work; drop provenance after a choice.
