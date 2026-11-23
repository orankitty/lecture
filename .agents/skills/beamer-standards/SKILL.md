---
name: beamer-standards
description: Enforce the user's locked marco.tex and source-specific Beamer conventions without replacing the existing lecture look.
---
# Source-Derived Beamer Standards
## Non-negotiable
- `marco.tex` is immutable. The filename is intentional; never rename or modify it.
- This pilot's source uses `\\documentclass[10pt,handout]{beamer}`, `\\input{../marco.tex}`. Presentation/notes class variants are present but commented out; don't toggle without authorization.
- `marco.tex` loads fontspec, xunicode, xltxtra, array, xcolor, verbatim, beamerthemesplit, beamerbasetemplates, graphics, graphicx, hyperref, multirow, tikz/pgfplots, algorithm, algorithmic, soul, colortbl, multicol; package list/order is locked.
- Madrid theme with rounded inner theme, rose color theme, small-caps serif structure, custom top section navigation and footer, alert orange and `\\code{}` blue. Preserve these details.
- Note page uses a custom infolines format and TH Sarabun New inside note text. Thai line-breaking configured. Fonts may be missing on a worker: flag as environment blocker, not change the locked macro.
- Preserve commands: `\\NextLine`, `\\NextHalfLine`, `\\RemoveLine`, `\\figureLocation`, `\\refLocation`, `\\textFont`, `\\rightNote`, and custom theorem/column settings.
## Slide conventions seen in LSCM_intro
- 10pt handout; title + outline + section navigation; descriptive short frame titles, `\\textsc{}` subheadings, emphasized alert/blue keywords, large white canvas, small source annotation, end bibliography.
- Current lecture has `\\note{}` in every active frame with `Purpose`, `Leading Question`, and itemized script; preserve and improve depth as needed.
- Overlays `\\only`, `\\uncover`, and `\\item<...>` are purposeful; compare handout versus presentation differently.
- Figures use relative paths via `\\figureLocation{}` and existing image assets; never substitute generated images without permission.
## Context-specific warning
- Prior graduate lecture generation preferences (16:9, CMU Serif, 88/540 for 9 hours) are NOT universal style constraints and must not override an existing Beamer deck or marco.tex.
