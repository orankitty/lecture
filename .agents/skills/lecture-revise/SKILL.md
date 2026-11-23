---
name: lecture-revise
description: Implement only approved targeted improvements in existing LaTeX/Beamer source, retaining macros, notes, overlays and compiled-baseline style.
---
# Targeted Beamer Revision
1. Check the approved plan; never assume unapproved changes are permitted.
2. Preserve originals on a Git tag or separate `original/` directory. Modify a working copy only.
3. Never edit `marco.tex`, alter package list, replace theme, change aspect ratio, or rewrite shared commands.
4. Edit only implicated frames; retain stable slide labels, \\section navigation, \\only/\\uncover incremental reveals, bibliography keys and existing notes.
5. For worked examples, provide context, decision owner, horizon, all data/units, constraints, assumptions, full solution, interpretation and recommended action; add reversal threshold when educationally relevant.
6. Prefer surgical changes to wholesale rewriting; report substantial changed sections and avoid needless text accumulation.
7. Preserve `\\note{}` and ensure each active slide retains `Purpose` and `Leading Question`. Teaching script may be expanded; don't invent sources.
8. Do not create or replace figures by default; write figure requests and await separate approval.
9. Output changed source files, `change_log.md`, and reference to approval IDs. Trigger `lecture-verify` before release.
