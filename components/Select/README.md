# Select

Select picks one value from a list too long for radios.

**Anatomy:** trigger (value + `chevron-down`) and listbox (options with optional right-aligned hint, check on the selected one, disabled options with a reason).

**Behaviour:** Radix/ARIA select pattern — Enter/Space/Down opens, type-ahead jumps, Esc closes. Over ~12 options, use a searchable combobox instead.

**Don't:** use for 2–3 options (radios or segmented control); hide disabled options that a user would expect to see.
