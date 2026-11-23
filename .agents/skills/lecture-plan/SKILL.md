---
name: lecture-plan
description: Convert a Beamer lecture audit into a prioritized, actionable frame-level improvement plan, preserving the user's intent and deferring figure generation.
---
# Prioritized Improvement Plan
- Read `lecture_audit.md`, `slide_map.csv`, course profile and original PDFs.
- For each proposed action record: `issue_id`, `frame_title`, `source_file:line`, `pdf_page`, category, severity, supporting evidence, proposed edit, instructional benefit, interaction with other slides, estimates of added/removed frames, and approval status.
- Classify action: RETAIN, CORRECT, CLARIFY, EXPAND, MERGE, REORDER, REMOVE, UPDATE_REFERENCE, FLAG_FIGURE.
- Distinguish factual inaccuracies from stylistic preferences. Avoid scope creep and assume no new figure-generation authorization.
- Surface course-level issues (CLO alignment, student prerequisites, lecture duration) separately from slide-level items.
- Propose sequence: critical factual fixes, high-priority pedagogical gaps, medium clarity, low copyediting.
- Output `improvement_plan.md`, `approved_changes.csv` template; stop for approval.
