# LSCM_network lecture QA

The source has 42 active frames and 1 dormant frames. The supplied PDF has 42 slide pages and 42 instructor-note pages. All pages were assigned using the numbered slide footer and, for notes, the preceding slide. Repeated footer numbers identify presentation overlays. The mapping records page correspondence from the supplied baseline.

Automation record. [GitHub Actions run 45228446654](https://github.com/orankitty/lecture/actions/runs/45228446654)

| Check | Result | Evidence |
| --- | --- | --- |
| Original source, PDF, and locked macro | PASS | The original uploads are unchanged on main. The review branch adds four reports and one separate TeX copy. |
| Active frame and baseline page mapping | PASS | 42 active source frames and 84 supplied PDF pages mapped by footer. Source section order is preserved. |
| Dormant TeX and overlays | PASS | 1 dormant frames and their enclosing tail are preserved byte for byte. The original class, overlay expressions, labels, links, and asset references are retained. |
| Teaching-note source | PASS | All 42 revised frames have a purpose, a leading question, and a teaching cue. The original note pages are available in the supplied PDF. |
| Targeted numerical/model checks | PASS | See computations below. |
| Bibliography and citation resolution | BLOCKED | The text scan found no `[?]` markers on the supplied slide pages. Supplied citation keys are preserved. The original databases were unavailable. |
| Original and revised XeLaTeX builds | BLOCKED | The original asset and bibliography preflight failed. Compilation was held at preflight. |
| Revised rendering, overflow, overlays, and note pages | NOT_RUN | Require a successful revision build and, for instructor notes, the original note font. Check the revised note length on the fixed-size pages. |
| Historical fact and source verification | NOT_RUN | The original case records, benchmark definitions, and figure datasets were not included. |
| GitHub Actions execution | BLOCKED | The run stopped at Validate Codex API secret. The interactive Codex session prepared this draft. |

## Numerical and model checks

- The signed graph balances add to zero. Shortest-path costs are 9, 8, and 8 across the three displayed alternatives. A positive sign on both node-3 arcs incorrectly removes the path through node 3.
- The transportation model has 70 real supply units and 90 demand units. Independently solving the corrected balanced LP with a zero-cost dummy gives objective 1,400 and 20 dummy units. One optimum supplies c1 from w2, 30 units of c3 and 10 units of c2 from w1, and 20 dummy units to c2.
- The facility example has 57 required units across five regions. In the displayed capacity units, four low-capacity plants supply at most 40. The demand constraint therefore has to be checked for each region j.
- The pictured three-node sub-tour selects three internal arcs. The displayed upper bound of two excludes that cycle. Other proper subsets must be considered for a complete formulation.

## Build dependencies

- The locked `../marco.tex` is present. The supplied baselines are 4:3 and use the source’s existing class settings.
- Missing figures or alternate overlay/note assets (5). Exact paths from `lectures/` appear in `figure_requests.md`.
- Original bibliography paths from `lectures/`: `../../../../Reference/Coordination.bib`.
- Original note rendering needs `TH Sarabun New`.
- Restore the original definition or include that supplies `\forIE`, `\forISE`. The supplied TeX and `marco.tex` do not define them.
- GitHub Actions requires `OPENAI_API_KEY` in repository Actions secrets.

Run these commands after restoring the original dependency layout. Review compiler and bibliography logs before publishing a revised PDF.

```bash
cd lectures
build_dir=$(mktemp -d)
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/original" LSCM_network.tex
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/revised" LSCM_network_revised.tex
```
