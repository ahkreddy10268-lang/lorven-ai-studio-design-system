# ChangeReview

Change review is where someone decides how a screenplay change affects work built from it, one scene at a time.

**Anatomy:** header (from → to versions, position "Scene 2 of 4 · 1 decided", previous/next) · per-scene row: source column (Courier `scene-heading` and `script-body`, deletions struck in `status-outdated-fg`, insertions underlined on `bg-selected`, margin asterisk for revised) and match column (`frame` icon + "Proposed match · not confirmed", frame thumbnails, the reason it matched, actions) · footer (reminder that approval does not change here; "Finish later").

**Actions per scene:** Confirm match (primary) · Choose other frames (secondary) · No frames affected (tertiary). A decided scene collapses to a one-line result with Undo.

**Behaviour:** confirming marks the matched frames **Check**; it never changes their approval. Progress is saved per decision. Keyboard: J/K previous/next scene; each decision is reversible until the review is closed.

**Content:** show the reason for every proposal ("Matched by scene number and heading"). Never show a percentage confidence unless engineering can stand behind it.

**Don't:** auto-confirm matches; move review decisions onto the overview; recolour revisions with Final Draft's revision page colours.
