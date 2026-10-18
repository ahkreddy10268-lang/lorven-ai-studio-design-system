# ProductSwitcher

The product switcher moves between Lorven's four products within the same project.

**Markup:** `l-menu` with `role="menu"`; items `l-menu__item` with the official product lockup in `.l-lockup` (`<img alt="Cine Scribe">`, 30px high, white plate so the black wordmark survives dark mode) and one line of project-specific state.

| State | Treatment |
| --- | --- |
| Current | `aria-current="true"`, `bg-selected` |
| Hover / focus | `bg-hover` / focus ring |
| Unavailable | `aria-disabled="true"`, secondary name, `lock` icon, reason in the description ("Not set up for this project") |

**Behaviour:** opens from the `switch` icon button in the context bar or with a shortcut; arrow keys move, Enter switches, Esc closes and returns focus. Switching keeps the project; the destination opens at the item linked to the current selection when one exists.

**Content:** the description is a status, not marketing: "42 frames · 3 need checking".

**Don't:** redraw, crop or recolour the lockups; shrink them below 30px; hide unavailable products (say why instead).
