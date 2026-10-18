# States

States cover what a surface shows when it is empty, loading, broken or unavailable.

| State | Treatment |
| --- | --- |
| Empty | `empty` icon (32px, `text-muted`), title says what is missing, one sentence on how to start, one or two actions |
| Loading | Skeletons shaped like the content (`skeleton`, `l-skel`), `aria-busy="true"` on the container; no spinners for lists |
| Error | `error` icon in `status-error-fg`, `role="alert"`, says work is safe, offers retry |
| Unavailable product | `unavailable` icon, says why and who can change it; other products keep working |

**Content:** "No storyboard yet" not "Nothing here!". Errors never blame the user.

**Don't:** use illustrations or emoji in states; show an empty state while data is still loading.
