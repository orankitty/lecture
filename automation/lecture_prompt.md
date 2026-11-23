# Codex task: Review + Revise + Verify Beamer lecture

Use the `Lecture basename` and `Operating mode` from the caller prompt.
Read `AGENTS.md` and `Beamer_Lecture_Improvement_Project.md` before editing.

## Input and path contract
- Source: `lectures/<lecture>.tex`
- Baseline visual: `lectures/<lecture>.pdf`
- Locked preamble/macros: `marco.tex`
- Original figures and bibliography: resolve actual original relative paths.
- Output source: `lectures/<lecture>_revised.tex`
- Output PDF, **only if honestly and successfully compiled**: `lectures/<lecture>_revised.pdf`
- Reports: `lectures/reports/<lecture>/lecture_audit.md`, `improvement_list.md`, `figure_requests.md`, `lecture_QA.md`.

## Review
1. Inventory all required files and missing dependencies. Compare active frames in source with baseline PDF pages, accounting for overlays and notes. Exclude dormant content after `\\end{document}` from active counts, but do not delete it.
2. Analyze all frames for correctness, terminology, assumptions, equations, numerics, teaching progression, examples, trade-offs, managerial implications, questions, references, and source-supported factual claims.
3. Examine PDF visual layout (projected font sizes, figures, graphics, charts, tables, overlays, crowding, legibility). Generate temporary raster pages in a build directory when helpful.
4. Write a slide-by-slide audit with page, frame, line, severity, evidence, action. Clearly separate confirmed errors, recommended improvements, and facts requiring verification.

## Revise (only if mode is revise)
5. Make targeted improvements, not a wholesale redesign. Keep the 2184408 undergraduate audience in view when applicable.
6. Use a COMPLETE copy of the original `.tex` and preserve relative `\\input` and `\\includegraphics` paths, original page geometry, Beamer theme, and intentional overlays. NEVER change `marco.tex`.
7. For EVERY active `frame`, maintain or improve `\\note{}` with `Purpose`, `Leading Question`, and actionable teaching guidance/anticipated answers. Keep course policy and administrative facts unchanged unless explicit authorization is provided.
8. Retain original figures, list figure proposals separately; do not generate or substitute any figure. Preserve official course descriptions and grading thresholds.

## Verify
9. Attempt original and revised XeLaTeX builds only with real dependencies. Build from the appropriate lecture directory so `../marco.tex` and graphics paths resolve. Use `latexmk -xelatex` with an isolated build directory. Do not fabricate font, figure, bibliography, or citation dependencies; if blocked, report exactly why and mark BLOCKED rather than PASS.
10. Recompute numerical examples independently. Check note presence, number of frames, warnings, text overflow, citation resolution, math, source/PDF agreement, and compare rendered PDF pages visually against original when build succeeds.
11. Place a successfully compiled revised PDF at its specified output path only after validation. If a prior revised PDF exists but current compile is blocked, do not present stale PDF as verified; remove or clearly flag it in the QA report.
12. Always write the reports even if blocked. State PASS/BLOCKED/FAIL/NOT_RUN for each test and list exact actionable dependencies. In audit mode do not edit the lecture or generate a revised file.

## Reports
`lecture_audit.md`: All  active frames, findings, and associated source/PDF references.
`improvement_list.md`: PDF page | title | source line | issue | evidence | severity | action | applied/deferred/approval.
`figure_requests.md`: Retain / Refine / Redesign / Replace / Add; no asset generation.
`lecture_QA.md`: Build commands, errors, dependency inventory, numerical verification, slide/note/citation counts, visual QA status, and explicit remaining limitations.
