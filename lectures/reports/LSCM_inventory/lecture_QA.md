# LSCM_inventory lecture QA

The source has 34 active frames and 1 dormant frames. The supplied PDF has 34 slide pages and 34 instructor-note pages. All pages were assigned using the numbered slide footer and, for notes, the preceding slide. Repeated footer numbers identify presentation overlays. The mapping records page correspondence from the supplied baseline.

Automation record. [GitHub Actions run 45228428995](https://github.com/orankitty/lecture/actions/runs/45228428995)

| Check | Result | Evidence |
| --- | --- | --- |
| Original source, PDF, and locked macro | PASS | The original uploads are unchanged on main. The review branch adds four reports and one separate TeX copy. |
| Active frame and baseline page mapping | PASS | 34 active source frames and 68 supplied PDF pages mapped by footer. Source section order is preserved. |
| Dormant TeX and overlays | PASS | 1 dormant frames and their enclosing tail are preserved byte for byte. The original class, overlay expressions, labels, links, and asset references are retained. |
| Teaching-note source | PASS | All 34 revised frames have a purpose, a leading question, and a teaching cue. The original note pages are available in the supplied PDF. |
| Targeted numerical/model checks | PASS | See computations below. |
| Bibliography and citation resolution | BLOCKED | The text scan found no `[?]` markers on the supplied slide pages. Supplied citation keys are preserved. The original databases were unavailable. |
| Original and revised XeLaTeX builds | BLOCKED | The original asset and bibliography preflight failed. Compilation was held at preflight. |
| Revised rendering, overflow, overlays, and note pages | NOT_RUN | Require a successful revision build and, for instructor notes, the original note font. Check the revised note length on the fixed-size pages. |
| Historical fact and source verification | NOT_RUN | The original case records, benchmark definitions, and figure datasets were not included. |
| GitHub Actions execution | BLOCKED | The run stopped at Validate Codex API secret. The interactive Codex session prepared this draft. |

## Numerical and model checks

- TV EOQ uses annual demand 12,000, ordering cost 4,000, and annual holding cost 100 dollars per TV. The radicand is 960,000 and its root is 979.80 TVs.
- Cartons have unconstrained EOQ 4,000 and annual relevant cost 6,000 THB. The 2,000 in-house cap raises that to 7,500 THB. Under the displayed maximum-excess storage charge, the paid-delivery rental option has continuous Q = 2618.61 and cost 7,165.15 THB/year at Q = 2,619.
- The strict free-delivery threshold first holds at 3,001 boxes (30,010 THB purchase value). With the case storage convention, annual relevant cost is 1,001 + 2,250.75 = 3,251.75 THB.
- Skis use net salvage 80, underage 150, and overage 20. The unrounded fractile 150/170 yields 468.68 pairs in the continuous calculation.

## Build dependencies

- The locked `../marco.tex` is present. The supplied baselines are 4:3 and use the source’s existing class settings.
- Missing figures or alternate overlay/note assets (18). Exact paths from `lectures/` appear in `figure_requests.md`.
- Original bibliography paths from `lectures/`: `../../../../Reference/Coordination.bib`.
- Original note rendering needs `TH Sarabun New`.
- Restore the original definition or include that supplies `\forIE`. The supplied TeX and `marco.tex` do not define them.
- GitHub Actions requires `OPENAI_API_KEY` in repository Actions secrets.

Run these commands after restoring the original dependency layout. Review compiler and bibliography logs before publishing a revised PDF.

```bash
cd lectures
build_dir=$(mktemp -d)
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/original" LSCM_inventory.tex
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/revised" LSCM_inventory_revised.tex
```
