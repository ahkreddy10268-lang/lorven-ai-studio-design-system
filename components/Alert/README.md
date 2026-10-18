# Alert

Alerts are inline messages tied to a place on the page: information, a warning, an error or a confirmation that should stay visible.

**Anatomy:** icon · title (what happened) · body (consequence and next step) · optional actions · optional dismiss.

| Variant | Border and icon | Role |
| --- | --- | --- |
| Info | `status-info-border`, `info` | `note` |
| Warning | `status-check-border`, `check-source` | `status` |
| Error | `status-outdated-border`, `error` | `alert` |
| Success | `border-default`, `approved` icon | `status` |

**Rules:** full thin border, never a thick coloured left edge; background stays the surface so text keeps its contrast. Errors persist until resolved; info and success may be dismissed.

**Don't:** use alerts for transient confirmations (Toast) or for decisions that block progress (ConfirmDialog).
