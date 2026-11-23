# Git_Action Beamer automation starter

Copy `.github/workflows/Git_Action.yml` and `automation/lecture_prompt.md` to your existing repository.

Required repo inputs: `AGENTS.md`, `Beamer_Lecture_Improvement_Project.md`, `marco.tex`, original `lectures/<lecture>.tex`, original `lectures/<lecture>.pdf`, and all referenced figures/BibTeX/font dependencies.

Add `OPENAI_API_KEY` as a GitHub Actions repository secret. Set workflow permissions to allow creation of pull requests (`Settings -> Actions -> General -> Allow GitHub Actions to create and approve pull requests`, if available), and ensure action token can write repository contents and pull requests. See workflow permissions note below.

To trigger:
  gh workflow run Git_Action.yml -f lecture=LSCM_intro -f mode=revise

Monitor:
  gh run list --workflow Git_Action.yml

NOTE: This workflow grants the job `contents: write` and `pull-requests: write` for the controlled publication step. Codex itself receives no GH_TOKEN and checkout uses `persist-credentials: false`.

The action does not overwrite `main`; it creates a branch and pull request. First run may be BLOCKED on missing figures, bibliography, or fonts; these are real build dependencies, not reasons to substitute placeholder images.
