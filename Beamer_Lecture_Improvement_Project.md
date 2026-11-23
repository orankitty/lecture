# Beamer lecture improvement project

`lectures/LSCM_intro.tex` is the editable source for the introductory undergraduate logistics and supply chain lecture. `lectures/LSCM_intro.pdf` is the supplied 25-page visual baseline. The locked root `marco.tex` sets the presentation theme, shared commands, bibliography style, and note layout.

Review the active source against the corresponding PDF pages. Retain the instructor's original examples and overlay structure. Use the notes to teach the decision, trade-off, and assumptions behind each example. Keep historical examples dated and distinguish evidence from hypotheses. Retain all text after `\end{document}` as dormant source.

Audit mode writes the four reports under `lectures/reports/<lecture>/`. Revise mode also writes `lectures/<lecture>_revised.tex`. Use the output contract in `automation/lecture_prompt.md` for the reports and optional compiled PDF. The review branch is the place to inspect the changes before merging.

Run `latexmk -xelatex` from the lecture directory with an isolated build output directory. `marco.tex` resolves figures through `../figures/` and bibliographies through `../../../../Reference/` relative to the lecture directory. Restore the original assets and path layout before building. The instructor note template requests `TH Sarabun New` when notes are rendered.
