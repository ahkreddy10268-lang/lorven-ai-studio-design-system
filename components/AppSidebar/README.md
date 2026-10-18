# AppSidebar

The app sidebar is the studio shell: global and project navigation on a deep navy ground (`bg-shell`) that frames every workspace.

**Anatomy:** master logo (white version, `lorven-studio-white.png`, transparent margin cropped only) · collapse button · global group (Projects, Search) · project group headed by the project name (Overview, then the four products) · spacer · Settings and account.

| Property | Values |
| --- | --- |
| Width | expanded 240px; collapsed 56px (icons only, names as tooltips, logo hidden) |
| Item state | default, hover (`shell-hover`), count badge (`l-badge--count`, things that need you), current (`aria-current="page"`, `shell-selected` + 2px `shell-indicator`), focus (ring in `shell-indicator`) |
| Availability tag | "Early access" on products not yet live for this account; the item still opens an honest explainer, never a fake workspace |

**Behaviour:** `[` toggles collapse and the choice persists per user. Below `bp-medium` the sidebar becomes a drawer opened from the toolbar. The shell is navy in both themes (`bg-shell`): the workspace reads as the lit stage. Product workspaces can nest one level of sub-navigation (sequences, acts) with a guide line; never deeper. Products are named in text with `product-*` icons; the official lockups are not used here.

**Don't:** add a fourth level of navigation; put actions here (they belong in the toolbar or command menu); use colour other than `shell-indicator` for the current item.
