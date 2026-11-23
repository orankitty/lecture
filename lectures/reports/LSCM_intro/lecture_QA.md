# LSCM introduction QA

The review draft contains revised TeX and the four reports. The supplied 25-page PDF was used as the visual baseline. A revised PDF requires a complete and verified XeLaTeX build.

## Checks

| Check | Status | Evidence |
| --- | --- | --- |
| Protected inputs | PASS | The committed original TeX, PDF, and `marco.tex` match the three uploads byte for byte. |
| Active frame mapping | PASS | Original and revised source each have 25 active frames in four sections. Every original active frame was matched to one page of the supplied 25-page handout using titles, content, section order, and footer numbers. |
| Dormant source | PASS | The four dormant frames and everything following `\end{document}` are preserved byte for byte. |
| Notes in source | PASS | Both sources contain notes on all 25 active frames. The revised notes each contain a purpose, a leading question, and an actionable teaching cue. The original contains nine placeholder questions and two notes without both headings. |
| Notes rendering | BLOCKED | The handout omits note pages. Rendering requires the missing assets and the note template's `TH Sarabun New` font. |
| Preamble, labels, and overlays | PASS | The document class and preamble, relative include and citation references, frame labels, link targets, and overlay specifications are preserved. |
| Official descriptions and course policy | PASS | The visible administrative frames’ policy and descriptions remain the same. Course identifier, email target, and grading interpretation are flagged for instructor confirmation. |
| Numerical examples | PASS | Recomputed the two price spreads and the trade scenario results below. |
| Historical chart measurements and claims | NOT_RUN | Original figure datasets and publications were unavailable for independent verification. The review flags the claims that need evidence. |
| Citation keys | PASS | All six active citation keys are retained and correspond to the six entries visible in the baseline bibliography. |
| Bibliography resolution | BLOCKED | The two original `.bib` databases are missing. The rendered bibliography and edition details cannot be regenerated or reconciled. |
| Original XeLaTeX build | BLOCKED | Preflight found missing original figures, bibliography inputs, and the source for `\forIE`. The build command was held at preflight. |
| Revised XeLaTeX build | BLOCKED | The draft preserves the same dependencies and build layout. The build command was held at preflight. |
| Compiler warnings, overflow, and undefined references | NOT_RUN | These checks require a complete XeLaTeX log. |
| Revised PDF comparison and visual verification | NOT_RUN | All baseline pages were visually inspected. Revised rendering, presentation overlays, and notes still need comparison. |
| GitHub Actions execution | BLOCKED | GitHub Actions run `45226314245` passed input validation and installed its tools. The Codex action received an empty API-key input. It skipped starting its API proxy and stopped while looking for the proxy's server-info file. This review was completed in the interactive Codex session. |

## Numerical verification

- Shirt supply chain, page 11. Using exact decimal subtraction, the distributor spread is \$41.34 − \$20.45 = \$20.89 and the retailer spread is \$52.72 − \$41.34 = \$11.38. Operating costs are unspecified, so these are price spreads.
- Local vs. global consumption, page 14. Local totals are \$750 for Thailand and \$700 for the USA. With one imported item per country and \$50 transport already included in each import price, the global total is \$500 per country. Savings are \$250 and \$200, or \$450 combined. Holding local prices fixed and varying the transport cost for each imported item separately, the break-even import costs are \$300 for software into Thailand and \$250 for suits into the USA.

## Build dependencies and commands

The locked `marco.tex` is present. The following dependencies are still unavailable.

- From `lectures/`, supply the original `../figures/../../../learning.png` path and the files in `../figures/scm_intro/`. The required names are `LiFungCountry.png`, `clothingSC.png`, `HowtoMadeAshirt.png`, `shirtRelatedIndustry.png`, `conflictObjective.png`, `LogisticVsGDP1.png`, `LogisticVsGDP2.png`, `worldLogisticPerGDP.png`, `workBank2014.png`, `Development02.png`, `dvdVSvcd` with its original extension, `SCM_MatFlow.png`, `futureSCM2.png`, `futureSCM3.png`, `futureSCM4.png`, and `futureSCM5.png`. The list includes presentation and note assets.
- Restore `../../../../Reference/Coordination.bib` and `../../../../Reference/logisticProvider.bib`, relative to `lectures/` as defined by `\refLocation`. The bibliography and learning image paths reach outside the repository in this checkout and require the original project layout or a separately approved dependency setup.
- Supply the existing definition or original package that provides `\forIE`. The macro is used in five active frame titles and has no definition in either supplied TeX file.
- Install `TH Sarabun New` when rendering instructor notes. The font is referenced by `marco.tex` and the local font inventory did not contain it. The local TeX installation also lacked `algorithm.sty`, `algorithmic.sty`, and `soul.sty`. GitHub Actions installed the wider TeX package set before its Codex action stopped.
- Set `OPENAI_API_KEY` in the repository’s Actions secrets before retrying the automated workflow.

Build from the lecture directory once the original inputs are present. Keep both output directories isolated and inspect their compiler and bibliography logs before comparing the PDFs.

```bash
cd lectures
build_dir=$(mktemp -d)
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/original" LSCM_intro.tex
latexmk -xelatex -interaction=nonstopmode -halt-on-error -outdir="$build_dir/revised" LSCM_intro_revised.tex
```
