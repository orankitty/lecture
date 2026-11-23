# Academic Beamer project instructions

## Immutable source of presentation configuration
- `marco.tex` is USER-LOCKED. Never edit, replace, format, reorder, or add packages to it; never silently override its settings in the lecture preamble.
- The actual user file is named `marco.tex` (not `macro.tex`). Resolve its `\\input{../marco.tex}` relative to the lecture's original project layout.
- Retain the declared packages, Madrid theme, horizontal section navigation, footer, color conventions, fonts, author/institute, macros, note-page template, and figure/reference path macros.
- Existing course `.tex` and its compiled PDF are two required evidence sources. The PDF is the baseline for *appearance*; the active `.tex` is the baseline for *editable content and notes*. The provided PDF is not evidence that the provided `.tex` can currently compile from an incomplete asset bundle.

## Workflow and approvals
1. Inventory assets, assess source–PDF correspondence, identify `\\end{document}` and exclude dormant source after it from active-slide mapping.
2. Audit active slides academically and visually; record findings with frame title, PDF page, source line, severity and evidence.
3. Write prioritized improvement plan; STOP for instructor approval before any substantive change.
4. Edit only approved ranges on a copy/branch. Preserve existing examples, effective slides, logical overlays and teaching cues.
5. Recompile, compare rendered PDFs, independently recalculate numerics, test notes and references. Document blocked checks rather than claiming success.
6. Publish `tex + student pdf + instructor notes pdf (when configured) + audit + changes + QA`; never overwrite the baseline.

## Teaching priorities
- Industrial Engineering decision-centered pedagogy: context, situation, model, fully worked example, interpretation/action, warning/limitations, summary.
- Match the level of each course: 2184408 undergraduate SCM is introductory; advanced graduate courses may require fuller mathematical depth. Never impose graduate-level scope on an undergraduate course.
- Examples must be self-contained: decision owner/horizon, alternatives, complete data, units, constraints, assumptions, calculations, managerial decision, and where appropriate reversal threshold.
- Preserve student engagement: Socratic questions, realistic industrial scenarios, careful comparison of trade-offs, not just definitions.
- Exactly one comprehensive integrated capstone when a new extended lecture request specifies a capstone; do not insert capstones into existing lectures without approval.
- Every active frame should retain a meaningful `\\note{}` with `Purpose` and `Leading Question`; enrich teaching script/time/source when the lecture standard or requested scope requires it. Never delete existing notes.

## Presentation and references
- Existing project style prevails over inferred generic 16:9/CMU Serif/color guidelines. Do NOT change aspect ratio, font/theme/colors, or packages of 2184408 merely to match other courses.
- Maintain user macros: `\\code{}`, `\\alert{}`, `\\NextLine`, `\\NextHalfLine`, `\\figureLocation{}`, `\\refLocation{}`; overlays are intentional pedagogy, not duplicates.
- Cite trustworthy textbooks/standards/journals and label historical vs current claims. Do not fabricate references, bibliographic keys, statistics, URLs or figure sources.
- Illustrations are phase-2 OPTIONAL: first propose `figure_requests.md`, generate/revise only after a separate authorization.
- Distinguish confirmed source-derived rules vs inferred historic preferences. Do not 'fix' substantive content while creating style metadata.
