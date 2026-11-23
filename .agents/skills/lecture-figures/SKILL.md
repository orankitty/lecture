---
name: lecture-figures
description: Produce a prioritized figure-review queue from existing PDFs/TEX; generate or edit figures ONLY on explicit later authorization.
---
# Deferred Figure Improvement
## Default mode: diagnose only
- Inspect original rendered figure and its location in source.
- Classify RETAIN, REFINE, REDESIGN, REPLACE, or ADD; explain conceptual weakness and visual/technical issue.
- Output `figure_requests.md`: slide/frame, original asset, teaching message, exact elements/units/axes, desired style, preferred editable medium, placement and priority.
- Do NOT modify/create visuals or `\\includegraphics` references until the user expressly chooses a figure or set for production.
## If authorized later
- Pure white background where appropriate, corporate vector style, minimal clear labels, distinct operationally meaningful icons, restrained navy/blue/teal/green/orange/gray palette, strong projection legibility; accuracy outranks decoration.
- Prefer TikZ/PGFPlots or editable SVG/PPT objects for diagrams when technical editability matters. Respect originals' meaning, evidence and source credit.
- Render final slide after insertion; compile and pass regression QA.
