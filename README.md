# lecture
## Purpose
Based on uploaded `marco.tex` (locked), `LSCM_intro.tex` and the 25-page `LSCM_intro.pdf`, plus prior course-generator requirements. Ready to copy into a local Codex project root.

## Installation
1. Copy `AGENTS.md` and `.agents/skills/` to the root of your own existing lecture repository.
2. Retain `marco.tex` exactly as-is in its actual location; do not install or copy the supplied macro as a replacement.
3. Put a copy of the `COURSE_PROFILE_example.yaml` (renamed `course_profile.yaml`) alongside the course lectures and adjust its paths.
4. Run review-only first: `Review this existing TEX+PDF with lecture-review; propose improvements; do not edit TEX or generate images.`
5. Approve the proposed changes before invoking `lecture-revise`; run `lecture-verify` after edits.

## Non-coding deliverables
- Source/PDF mapping; pedagogical and visual audit; prioritized change plan; figure request backlog (no images); traceable edit and QA logs.

## Do not silently generalize
- `marco.tex` is the authoritative theme for **this** course, and a locked constraint. Historic graduate material uses additional preferences not always present in the SCM intro deck. A reusable global skill must follow each course's own master source.

## References
- First-hand: `marco.tex`, `LSCM_intro.tex`, `LSCM_intro.pdf` (uploaded pilot files).
- Prior-generation context: Engineering Economy and Cost Accounting (decision-centered examples, graduate depth, instructor note scripts, one integrated capstone, technical QA).
- Technical: LaTeX Beamer manual, CTAN latexmk documentation, Codex skills and AGENTS.md instructions.
