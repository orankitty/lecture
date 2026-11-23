---
name: lecture-review
description: Inspect paired existing Beamer TEX and compiled PDF, map active frames and overlays, and audit academic content, visual quality, and teaching notes without editing source.
---
# Lecture Review (two-source audit)
1. Read immutable `marco.tex` and the lecture main `.tex` without modification; identify path dependencies and active content before the first `\\end{document}`.
2. Read the supplied compiled PDF: inspect pages visually, count pages, detect overlays, compare titles/text/figures, identify potential divergence between TEX and PDF. An equal frame/page count is supporting evidence only, not proof of identical builds.
3. Create a `slide_map.csv` with source file, source line, frame title, notes status, PDF page(s), section, and evidence status. When overlays exist, one frame may cover several presentation pages; handout mode commonly collapses overlays.
4. Audit per slide: learning goal, prerequisite level, correctness, assumptions, example data and units, source currency, decision/trade-off, questions, coherence, slide density/legibility, typography, missing graphics.
5. Distinguish active source and dormant frames after `\\end{document}`. Never silently delete dormant content.
6. Prioritize `Critical` (wrong concepts/calculations), `High` (missing/incomplete evidence or core pedagogy), `Medium` (weak explanation/readability), `Low` (copyediting).
7. Output `lecture_audit.md`, `slide_map.csv`, `dependency_report.md` and separate `figure_requests.md`. No source edits.
## Stop rule
Ask for academic approval of the plan before any substantive changes, unless the user explicitly authorizes direct revision.
