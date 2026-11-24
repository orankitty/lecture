# LSCM_strategy lecture QA

The source has 43 active frames and 6 dormant frames. The supplied PDF has 43 slide pages and 43 instructor-note pages. All pages were assigned using the numbered slide footer and, for notes, the preceding slide. Repeated footer numbers identify presentation overlays. The mapping records page correspondence from the supplied baseline.

Automation record. [GitHub Actions run 45228451833](https://github.com/orankitty/lecture/actions/runs/45228451833)

| Check | Result | Evidence |
| --- | --- | --- |
| Original source, PDF, and locked macro | PASS | The original uploads are unchanged on main. The review branch adds four reports and one separate TeX copy. |
| Active frame and baseline page mapping | PASS | 43 active source frames and 86 supplied PDF pages mapped by footer. Source section order is preserved. |
| Dormant TeX and overlays | PASS | 6 dormant frames and their enclosing tail are preserved byte for byte. The original class, overlay expressions, labels, links, and asset references are retained. |
| Teaching-note source | PASS | All 43 revised frames have a purpose, a leading question, and a teaching cue. The original note pages are available in the supplied PDF. |
| Targeted numerical/model checks | NOT_RUN | Cases were reviewed for interpretation. Historical data and numerical business claims were unavailable for independent reproduction. |
| Bibliography and citation resolution | BLOCKED | Visible unresolved citation markers on baseline PDF pages 3, 13, 17, 19, 29, 37, 57, 61, 63, 65, 67, 69. Supplied citation keys are preserved. The original databases were unavailable. |
| Original and revised XeLaTeX builds | BLOCKED | The original asset and bibliography preflight failed. Compilation was held at preflight. |
| Revised rendering, overflow, overlays, and note pages | NOT_RUN | Require a successful revision build and, for instructor notes, the original note font. Check the revised note length on the fixed-size pages. |
| Historical fact and source verification | NOT_RUN | The original case records, benchmark definitions, and figure datasets were not included. |
| GitHub Actions execution | BLOCKED | The run stopped at Validate Codex API secret. The interactive Codex session prepared this draft. |

## Build dependencies

- The locked `../marco.tex` is present. The supplied baselines are 4:3 and use the source’s existing class settings.
- Missing figures or alternate overlay/note assets (54). Exact paths from `lectures/` appear in `figure_requests.md`.
- Original bibliography paths from `lectures/`: `../../../../Reference/Coordination.bib`, `../../../../Reference/logisticProvider.bib`.
- Original note rendering needs `TH Sarabun New`.
- Restore the original definition or include that supplies `\forIE`. The supplied TeX and `marco.tex` do not define them.
- GitHub Actions requires `OPENAI_API_KEY` in repository Actions secrets.

Run these commands after restoring the original dependency layout. Review compiler and bibliography logs before publishing a revised PDF.

```bash
cd lectures
build_dir=$(mktemp -d)
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/original" LSCM_strategy.tex
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/revised" LSCM_strategy_revised.tex
```
