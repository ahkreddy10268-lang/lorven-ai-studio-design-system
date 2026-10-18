# PromptComposer

The prompt composer is where a person asks Lorven to generate, with the context it will use and the effect it will have stated before they press Generate.

**Anatomy:** context row ("Using" + removable reference chips + Add context) · text field · bar with the consequence note, settings (variations) and the primary Generate action (`aperture` icon).

| State | Treatment |
| --- | --- |
| Ready | Generate enabled; note states the effect ("Makes 3 new frames. Your current frames stay.") |
| Generating | Field read-only, Generate becomes Stop, note becomes a live `role="status"` |
| Unavailable | Disabled with the reason in the placeholder and note ("No scene selected.") |

**Behaviour:** ⌘↵ generates. Context chips are explicit — nothing the user can't see is sent. Settings open a popover; only settings the product actually supports appear.

**Don't:** turn the composer into a chat thread; hide what will be replaced; show model names, tokens or credits unless the product really meters them.
