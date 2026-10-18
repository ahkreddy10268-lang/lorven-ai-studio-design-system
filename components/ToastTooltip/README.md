# ToastTooltip

Toasts confirm what just happened and offer Undo; tooltips name icon-only controls and explain unavailable ones.

**Toast:** bottom-centre, `bg-inverse`, one sentence, one action (Undo, Retry), dismiss. Success stays 6s (longer when it holds Undo: 10s, pausing on hover/focus); errors persist until dismissed. `role="status"` or `role="alert"`.

**Tooltip:** appears after 500ms hover or immediately on keyboard focus; names the control and its shortcut. Never hold essential information or interactive content.

**Don't:** stack more than 3 toasts; use toasts for errors that need a decision (use an inline state or dialog).
