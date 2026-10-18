# CommandMenu

The command menu (⌘K / Ctrl K) reaches every action and destination by name, so the interface can stay quiet.

**Anatomy:** search field with Esc hint · grouped results (Actions first, then Go to) · matched text in bold · keyboard shortcut at the row end · footer with key hints.

**Behaviour:** opens over any surface as a modal (`aria-modal`, combobox + listbox pattern); typing filters; Up/Down moves (`aria-selected`), Enter runs, Esc closes and restores focus. Results are scoped to the current project and product first. Actions that are unavailable appear with a reason rather than disappearing.

**Content:** verb-first action names that match button labels exactly ("Generate frames for scene 12").

**Don't:** use it as the only route to a primary action; show more than 8 results per group before "Show all".
