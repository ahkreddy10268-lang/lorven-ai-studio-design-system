# Evidence and research

## Evidence register

**1 · Confirmed from supplied materials**
- The V2 design-system brief: four products and their scopes; required status vocabulary (approval, currency, attention); the rule that approval and currency are independent; Switzer proposed as interface face; master identity with warm gold/orange/red accents; product lockups with black wordmarks and cyan icon discs; "The Salt Orchard" as the fictional sample project.

- Logo files (Logos group): master lockup in colour, white and black PNG; product lockups as PNG, JPG, PDF and SVG. Sampled: product disc cyan #00bdff; master gold gradient #b07908–#f7e56f (mid #e1c261); STUDIO gradient #ee7a43 → #c1272d. Product wordmarks are black only; the master has a white version.
- Product SVGs: the originals (in the uploaded zip) are sound, but each wordmark is live text in Riosark (NazmulsDesign, licence unknown). The copies in this system's asset store had their `<style>` blocks stripped on upload and render black. The stored Cine Sketch also differs in geometry from the zip version.
- Switzer variable and static files (upright and italic, 100–900). Embedded licence record: © Indian Type Foundry, terms at fontshare.com/terms, embedding unrestricted (fsType 0). The supplied Fontshare Free Font EULA (FFL.txt, March 2021) grants personal and commercial use in any media including web and apps; it prohibits redistributing the files, passing them to external service providers, and serving them over the internet for font replacement without written consent. Credits are optional. ITF's public description matches ([ITF](https://www.indiantypefoundry.com/news/introducing-fontshare)).
- Also supplied: Nexa (Light, Bold), an unnamed font file ("behance-…", licence unknown), launch posters, two earlier logo explorations, and earlier product screen PDFs. The screen PDFs were deliberately not used as visual reference (standing project decision).

**Legacy design file:** a summary of the earlier Figma file was supplied in the brief; the file itself was not opened here. See *Legacy system*.

**Still not available:** product foundation and requirements documents, Exploration 01 and 02, the hybrid overview and change-review prototype, producer feedback, user research. Claims that would depend on them are classified as hypotheses or open decisions.

**2 · Direct stakeholder requirements** (from the brief)
- Light and dark as first-class modes; WCAG 2.2 AA target; status never by colour alone.
- Logos preserved exactly; Switzer only after licence verification.
- Original icon set; no sparkle-for-AI.
- No implied backend sync, guaranteed scene matching or verified confidentiality.
- No high-fidelity full-screen UI before at least one 15–20 minute usability pilot (standing project decision); this system therefore proves itself at component level.

**3 · Product design hypotheses** (unvalidated — test in the pilot)
- H1. Users act faster when the overview leads with a single "what needs me" band than with a dashboard of equal-weight panels.
- H2. Users confuse "approved" with "up to date" unless the two are visually separated by form, not just colour.
- H3. Writers trust a change summary more when changes are shown in screenplay typography with revision marks, as in their writing tool.
- H4. A proposed scene match is acceptable to users only if it shows why it matched and stays unconfirmed until a person acts.
- H5. Script work is read better in light mode, storyboard art judged better in dark.

**4 · Unresolved decisions** — see *Open decisions*.

## Live product site (lorvenaistudio.com, read October 2026)

- **Modules and availability:** Cine Sketch is listed as available; Cine Scribe, Pitch Craft and Cine Flow are in development with early access. The system's shell shows this honestly ("Early access" tags) instead of implying four live products.
- **Naming:** the site writes the products as two words (Cine Sketch, Pitch Craft, Cine Flow), matching the lockups; the V2 brief wrote them as one word. This system follows the site and lockups.
- **Claimed capabilities (site text, not verified in the app):** screenplay drafts from a logline, treatment or notes; tone adaptation from earlier scripts; storyboard frames with adjustable camera angle, framing and lighting; shot templates with character, location and camera metadata; pitch decks with logline, synopsis and mood direction; linked scripts, schedules and notes with stale-file and version-conflict flags. These shaped the AI and creative components (composer context, shot metadata in frames and inspector, currency states).
- **Process language:** Upload → Generate → Refine → Deliver. The AI components follow the same arc: context in, generation status, review, accept.
- **Not inspected:** the application itself sits behind Google sign-in at /login; no screens, routes, stack or components were verified. No codebase was available.

## Product audit (public documentation only)

Scope: vendor documentation and feature pages, read October 2026. No hands-on product sessions; interface layouts, density and theming were **not** observed and are not claimed. Celtx's scheduling page could not be retrieved, so Celtx is not assessed.

| Product | Observed (from documentation) | Interpretation for Lorven |
| --- | --- | --- |
| Final Draft | Revision Mode marks new or changed text in the active revision set; sets follow the industry colour sequence (White, Blue, Pink, Yellow…); a margin asterisk marks revised lines; revised page margins can take the set colour. [kb.finaldraft.com](https://kb.finaldraft.com/hc/en-us/articles/27813588722708-How-do-I-use-Revision-Mode) | Writers already read "asterisk in the margin = changed". Reuse it in `ChangeReview` and the `revised` icon. Do **not** reuse revision page colours as status colours — they carry a different, established meaning. |
| Boords | Comments pin to individual frames; each version carries a status from Draft to Approved; sign-offs are logged with name and time; new versions carry open threads forward; guests review by link without accounts. [boords.com/collaborate](https://boords.com/collaborate) | Approval-per-version is an established pattern, so Lorven's differentiator is not approval itself but **currency** — knowing when approved work has drifted from its script. |
| StudioBinder | Importing a script creates per-scene shot lists; shot tagging places the script next to the list so lines become shots; lists can be shared view-only and commented. [studiobinder.com](https://www.studiobinder.com/shot-list-storyboard/) | Script-to-shot linking is expected. The gap is what happens to those links when the script changes — the case `ChangeReview` designs for. |

## Observations → decisions

| Evidence | Implication | Design decision | Confidence | Open question |
| --- | --- | --- | --- | --- |
| Brief: approval and currency are independent | One combined status would hide drift in approved work | Three status families with three forms (filled / outlined / uncontained) | High | Does "Check" read as "verify" to producers? (pilot) |
| Final Draft revision asterisk | Writers recognise margin marks | Asterisk + Courier excerpts in `ChangeReview` | Medium | Do non-writers (DPs, producers) need a plainer cue? |
| Boords: per-version approval is standard | Approval alone does not differentiate | Lead the overview with currency-driven decisions (`DecisionBand`) | Medium | H1 untested |
| StudioBinder: script-linked shot lists | Links break silently when scripts change | Every derived asset shows its source (`VersionReference`) | Medium | How are matches computed? (engineering) |
| Logos: master gold gradient and orange→red STUDIO | Gold as action collides with amber Check | Warm colours reserved for brand surfaces; action is electric blue | High (rendered in Directions) | — |
| Logos: disc cyan #00bdff, wordmarks black-only | Bright cyan UI would compete with marks; black lockups vanish on dark | Action ramp on the disc hue but deeper; lockups always on a white plate in dark | High | Will a reversed lockup be made? |
| Dense production lists | 16px body would cost rows | `body` 14/20, `row-min` 56px, `control-md` 32px | Medium | Validate on long shot lists |

## Visual directions

Both directions were applied to the same decision band, asset row, primary button and status chips (see the **Directions** card).

| Criterion | A · Cinematic editorial | B · Precision workspace |
| --- | --- | --- |
| Status clarity | Fails: gold primary sits beside amber Check; in light mode gold must darken to pass 4.5:1 and becomes the Check colour | Blue action is distinct from every status hue |
| Identity | Strong brand echo, but spends the brand on buttons | Brand stays on brand surfaces; action shares the product discs' hue |
| Readability in both themes | Dark-led; light mode feels like an afterthought | Both themes hold hierarchy |
| Workflow density | Editorial spacing costs rows | Tight, aligned, tabular |
| Risk | Looks premium in a mock-up, ambiguous in use | Can feel cold if brand surfaces are neglected |

**Recommendation: B, with A's restraint on brand surfaces.** The product UI follows Direction B. Direction A's warm, deep treatment belongs to the studio shell, the project cover and marketing — places where nothing has a status.
