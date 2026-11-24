# LSCM_decision lecture QA

The source has 24 active frames and 4 dormant frames. The supplied PDF has 24 slide pages and 24 instructor-note pages. All pages were assigned using the numbered slide footer and, for notes, the preceding slide. Repeated footer numbers identify presentation overlays. The mapping records page correspondence from the supplied baseline.

Automation record. [GitHub Actions run 45228416108](https://github.com/orankitty/lecture/actions/runs/45228416108)

| Check | Result | Evidence |
| --- | --- | --- |
| Original source, PDF, and locked macro | PASS | The original uploads are unchanged on main. The review branch adds four reports and one separate TeX copy. |
| Active frame and baseline page mapping | PASS | 24 active source frames and 48 supplied PDF pages mapped by footer. Source section order is preserved. |
| Dormant TeX and overlays | PASS | 4 dormant frames and their enclosing tail are preserved byte for byte. The original class, overlay expressions, labels, links, and asset references are retained. |
| Teaching-note source | PASS | All 24 revised frames have a purpose, a leading question, and a teaching cue. The original note pages are available in the supplied PDF. |
| Targeted numerical/model checks | NOT_RUN | Cases were reviewed for interpretation. Historical data and numerical business claims were unavailable for independent reproduction. |
| Bibliography and citation resolution | BLOCKED | The text scan found no `[?]` markers on the supplied slide pages. Supplied citation keys are preserved. The original databases were unavailable. |
| Original and revised XeLaTeX builds | BLOCKED | The original asset and bibliography preflight failed. Compilation was held at preflight. |
| Revised rendering, overflow, overlays, and note pages | NOT_RUN | Require a successful revision build and, for instructor notes, the original note font. Check the revised note length on the fixed-size pages. |
| Historical fact and source verification | NOT_RUN | The original case records, benchmark definitions, and figure datasets were not included. |
| GitHub Actions execution | BLOCKED | The run stopped at Validate Codex API secret. The interactive Codex session prepared this draft. |

## Build dependencies

- The locked `../marco.tex` is present. The supplied baselines are 4:3 and use the source’s existing class settings.
- Missing figures or alternate overlay/note assets (14). Exact paths from `lectures/` appear in `figure_requests.md`.
- Original bibliography paths from `lectures/`: `../../../../Reference/Coordination.bib`.
- Original note rendering needs `TH Sarabun New`.
- GitHub Actions requires `OPENAI_API_KEY` in repository Actions secrets.

Run these commands after restoring the original dependency layout. Review compiler and bibliography logs before publishing a revised PDF.

```bash
cd lectures
build_dir=$(mktemp -d)
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/original" LSCM_decision.tex
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/revised" LSCM_decision_revised.tex
```
