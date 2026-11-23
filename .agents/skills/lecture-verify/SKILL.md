---
name: lecture-verify
description: Compile and regression-test revised Beamer TEX against the provided baseline PDF while explicitly reporting missing dependencies and unresolved checks.
---
# Build and Verify
1. Check that all `\\input`, `\\includegraphics`, bibliography databases and installed fonts are present. Never substitute placeholders for final release without explicit authorization.
2. Compile in a separate build workspace using XeLaTeX/latexmk, preserving relative directory layout. Do not write build artifacts into `original/`.
3. Run source checks: active frame count, frame labels/section order, note coverage, Purpose/Leading Question coverage, bibliography/link references, accidental content after `\\end{document}`.
4. Numerics: independently recalculate important equations and examples with Python/R or manual checks; record test inputs/results/units.
5. Render original and updated PDFs at comparable DPI, compare corresponding frames (including overlays), manually inspect critical figure/text changes. PDF binary equality is not required.
6. Verify compilation log for errors, missing files, undefined references, overfull/underfull warnings, and font substitutions; inspect whether warnings affect appearance.
7. Produce `qa_report.md` with PASS, FAIL, BLOCKED, or NEEDS_REVIEW for each check. Never report PASS when the compiler merely emitted a partial PDF.
8. Release only when critical checks pass and the instructor approves the substantive results.
## Known pilot condition
- LSCM_intro.tex includes `\\input{../marco.tex}` and external assets under `../figures` and `../../../../Reference` paths. With only the three uploaded files, compilation stops at missing `learning.png` (first encountered external figure). This is a dependency blocker, not proof that existing source is invalid.
