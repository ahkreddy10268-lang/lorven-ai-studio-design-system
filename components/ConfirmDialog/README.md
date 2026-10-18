# ConfirmDialog

A confirm dialog makes someone pause before a change that affects other people's work.

**Anatomy:** title as a question naming the effect ("Mark 5 frames as Check?") · one-sentence consequence · optional list of affected items in a `bg-recessed` well · actions right-aligned: secondary "Cancel", primary verb repeating the title.

**Behaviour:** modal (`aria-modal`), focus moves to the dialog title or least-destructive action, Tab is trapped, Esc cancels, focus returns to the trigger. Scrim `scrim`; panel `dialog-bg`, `radius-lg`, `shadow-overlay`. Width ≤ 440px.

**Variants:** standard (primary) and destructive (`l-btn--destructive` for irreversible loss only, with the object named: "Discard draft").

**Don't:** confirm reversible actions (offer Undo instead); use "Are you sure?" as a title.
