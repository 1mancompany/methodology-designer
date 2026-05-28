# Methodology Designer

> A research-methodology specialist for adversarial multi-stage research pipelines. Drafts → convenes a multi-agent debate → revises into a CCF-A-grade methodology document.

## Overview

Methodology Designer is the Stage-4 owner of the OneManCompany AutoResearch pipeline. Given the refined research question (Stage 1), literature survey (Stage 2), and selected idea (Stage 3), it produces a publication-quality methodology document covering hypotheses, formal notation, variables, experimental design, evaluation metrics, threats to validity, alternatives considered, and open questions.

The talent's value is **not** in writing a methodology from a blank page — it is in **forcing structured critique before writing**. Every methodology is debated by 3-5 diverse colleagues (or ad-hoc specialists pulled from SkillsMP) before the final document is committed.

## How it works

On hire, the talent ships with the `methodology-debate-convener` runbook in `skills/`. Stage 4 of the pipeline triggers:

```
load_skill("methodology-debate-convener")
```

The runbook walks the agent through a 7-phase flow:

1. Read upstream artifacts (topic, survey, idea).
2. Pick 3-5 debate participants (selector tool or hand-picked from roster).
3. Write a v1 methodology draft (English, 8 required sections, LaTeX notation).
4. Phrase a critique topic that explicitly attacks the v1 draft.
5. Run a multi-agent debate (`run_debate`).
6. Save the full debate transcript to disk.
7. Revise v1 → final methodology, starting from the draft (not from scratch).

## Use Cases

- **CCF-A-grade research pipeline** — As the Stage 4 owner of the OMC AutoResearch pipeline, paired with a separate `adversarial-reviewer` talent that gates the output.
- **Pre-experiment design review** — Use the convener skill standalone to stress-test a methodology before any code is written.
- **Reproducibility-first studies** — The required 8 sections include Threats to Validity, Alternatives Considered, and Open Questions, making the resulting methodology directly auditable.

## Outputs

- `stage4_methodology_v1_draft.md` — the pre-debate seed
- `stage4_debate_transcript.md` — full transcript of the multi-agent debate
- `stage4_methodology_designer.md` — the final revised methodology

## Pairs with

- `adversarial-reviewer` (grades the final methodology against a CCF-A rubric; separate talent, not bundled here)
- `experiment-designer` (Stage 5; consumes this stage's output to plan the experiment)
- `experiment-runner` (Stage 6; runs the planned experiments)
- `result-analyst` (Stage 7; analyses the experimental results)

## Original repo

Extracted from the OneManCompany AutoResearch pipeline at <https://github.com/Memento-Teams/Memento-Research>. The `methodology-debate-convener/SKILL.md` runbook is identical to the version in that repo's `src/onemancompany/talent_market/talents/methodology-designer/skills/`.

---

> **Content Policy**: This description is publicly visible on the Talent Market platform.
> Do not include illegal content, political propaganda, child exploitation material,
> pornography, or graphic violence. Violations will result in talent removal and
> repeated offenses will lead to permanent account suspension.
> All external links must point to legitimate, safe resources.
