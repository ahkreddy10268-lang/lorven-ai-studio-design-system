# SelectionControls

Checkbox, radio and switch let people set options, each with a visible label and a 24px target.

- **Checkbox** for independent options and multi-select lists; supports indeterminate for partial selection.
- **Radio** for one choice among 2–5 visible options; group with `role="radiogroup"` and a label.
- **Switch** for a setting that takes effect immediately (no Save). Use a checkbox when a Save is needed.

**States:** default, checked, indeterminate (checkbox), focus (`focus-ring`), disabled (with reason nearby). Checked fill is `action-primary`; marks are `text-on-action`.

**Don't:** use a switch inside a form that has a submit button; label a switch with on/off words.
