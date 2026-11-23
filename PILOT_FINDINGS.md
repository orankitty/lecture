# Initial source/PDF pilot findings — LSCM Introduction

## Confirmed
- `marco.tex` is locked and defines a custom Madrid/rounded/rose Beamer style, navigation headline and footline, author and institution, commands and note-page formatting.
- `LSCM_intro.tex` uses `\documentclass[10pt,handout]{beamer}` and `\input{../marco.tex}`.
- Active source before `\end{document}`: **25 frames**, **25 note commands**, four named sections. Compiled baseline PDF: **25 pages**. Counts align but full source–PDF equivalence remains unverified.
- Source after `\end{document}`: **4 dormant frames**. They should not be mistaken for active lecture material.
- Existing lecture uses `\only`, `\uncover`, incremental items, real-world examples, discussion prompts, citation keys, a reference frame, and relative `\figureLocation`/`\refLocation` paths.
- The PDF confirms the blue/purple title/header style, horizontal section navigation, footer with lecture version/page counts, and orange/blue emphasis.

## Build test
- Attempted XeLaTeX compilation with the two supplied TEX files in their expected relative layout. Build stopped on missing external `learning.png` (`../figures/../../../learning.png`), after producing an incomplete 2-page PDF. **No successful baseline rebuild is claimed.** Other external images and bibliography files are not supplied in this pilot bundle.

## Review findings requiring attention (no edits made)
1. The dormant content after `\end{document}` is an archive/maintenance concern; decide whether to place it in a separate archival file or leave untouched.
2. The source uses an email hyperlink whose target and displayed email differ; check intentionality in contact-info slide.
3. The source and PDF include time-sensitive policies, contact details, source claims and business examples; check against the current course offering before updating.
4. All 25 active frames contain `\note{}`, but only 23 have explicit `Purpose` and `Leading Question` labels. The `Issues in LSCM` and `Reference` frames lack these labels. Note depth and source quality vary.
5. Image and bibliography dependencies are needed for a reproducible post-edit build; defer figure redesign until separately authorized.

## Distinguishing historical preferences
- Prior graduate lecture-generator requirements include full scenario-to-decision examples, one integrated capstone on longer generated decks, and richer instructor note scripts; these are strong conditional preferences, not grounds to rewrite a short SCM introductory lecture or change `marco.tex`.
