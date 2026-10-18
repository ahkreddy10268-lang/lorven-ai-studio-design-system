# Badge

Badges carry a count or a "New" marker — never a workflow status (use StatusChip for that).

| Variant | Use |
| --- | --- |
| `l-badge--count` | Things waiting for the viewer (navigation, tabs). Electric blue, `radius-full`. |
| `l-badge--neutral` | Plain totals (comments, frames). |
| `l-badge--new` | A feature or template introduced recently; remove after 30 days. |
| `l-badge--dot` | Unread marker where a number adds nothing; needs an accessible label. |

**Rules:** counts over 99 show "99+". A count badge's label says what it counts ("2 need you"). Don't put badges on every nav item.
