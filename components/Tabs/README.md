# Tabs

Tabs switch between views of the same object without leaving it.

**Markup:** `role="tablist"` container `l-tabs`; each `l-tab` has `role="tab"` and `aria-selected`. Optional count `l-tab__count` (tabular figures).

**Behaviour:** Left/Right arrows move between tabs, Home/End jump; activation on focus is fine for local content, manual activation (Enter) when a tab loads data. Active indicator is a 2px `action-primary` underline.

**Content:** 1–2 words, sentence case. Counts only when they change a decision ("Changes 4").

**Don't:** use tabs for steps in a sequence (use the review's previous/next), or for more than 5 views; nest tabs.
