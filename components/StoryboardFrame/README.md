# StoryboardFrame

A storyboard frame shows one shot: artwork at the project's aspect ratio, its shot number and the shot data a crew needs.

**Anatomy:** 16:9 art area (letterboxed on `frame-letterbox`; respects the project ratio) · shot number top-left · currency chip top-right when not current · provenance bottom-left · metadata line: shot size (bold abbreviation), angle, lens.

| State | Treatment |
| --- | --- |
| Default / hover | Hover shows quick actions (Inspect, Compare) |
| Selected | 2px `border-selected` outline, 2px offset — artwork never tinted |
| Generating | Dashed edge, skeleton, "Generating…" |
| Check / Outdated | Currency chip on a solid plate over the art |

**Content:** shot sizes use industry abbreviations (WS, MS, CU, ECU) with full names in the inspector.

**Don't:** crop artwork to fit a card; put text over the centre of the image.
