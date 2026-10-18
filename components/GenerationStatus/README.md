# GenerationStatus

Generation status reports what an AI request is doing right now, using only facts the system knows.

| State | Shows |
| --- | --- |
| Queued | Why it's waiting; Cancel |
| Generating | What is being made and elapsed time; indeterminate bar; Stop |
| Partial | Real counts ("2 of 3 frames ready"), one segment per item; review what's ready |
| Stopped | What was kept and that nothing else changed |
| Failed | Plain cause if known, "Nothing was changed", Try again |
| Ready | That results are not yet applied; Review |

**Rules:** never show a percentage or time estimate the service doesn't provide. Segments appear only when the item count is known. Running and partial use `role="status"`; failure uses `role="alert"`. With reduced motion the bar stops animating.

**Don't:** report a request as done when results still need review; auto-apply results.
