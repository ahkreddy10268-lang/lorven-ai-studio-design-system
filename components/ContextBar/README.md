# ContextBar

The context bar keeps the project and source in view while someone works inside one product.

**Contains:** product switch button → breadcrumb (project › product › current item) → spacer → source reference (`history` icon, source version, compact currency chip) → one tertiary action.

**Behaviour:** sticky at the top (`z-sticky`), `bg-recessed` via `context-bar-bg`, 40px tall. The source reference updates when the source changes; it never auto-applies changes. At compact widths the breadcrumb collapses to the current item and the source becomes an icon button that opens the reference.

**Keyboard:** breadcrumb is a `nav` with `aria-label="Breadcrumb"`; current item is plain text, not a link.

**Don't:** add product navigation, search and notifications here — this bar is for context, not chrome. Never show more than one action.
