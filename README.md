# Methodology Designer

A Talent Market talent that owns **Stage 4 (Methodology Design)** of an
adversarial multi-stage research pipeline.

Given the refined research question, literature survey, and selected idea
from upstream stages, it:

1. Drafts a v0 methodology (8 sections, English, LaTeX notation).
2. Convenes a 3-5 person multi-agent debate to critique the draft.
3. Saves the full debate transcript.
4. Revises the draft into a CCF-A-grade final methodology document.

The debate-first workflow is the value proposition — it forces structured
critique before the methodology is committed, surfacing fatal flaws while
they are still cheap to fix.

## Install

Register the repo URL on [Talent Market](https://one-man-company.com/):

```
Add Talent → paste https://github.com/YihangChen9/methodology-designer
```

Or via API:

```bash
curl -X POST https://one-man-company.com/api/v1/repos \
  -H "X-API-Key: tm_live_..." \
  -H "Content-Type: application/json" \
  -d '{"url": "https://github.com/YihangChen9/methodology-designer"}'
```

## Repo layout

```
methodology-designer/         ← talent root (matches profile.yaml `id`)
├── profile.yaml               agent metadata (id, role, system prompt, …)
├── DESCRIPTION.md             public-facing description
├── avatar.jpg                 avatar image
├── skills/
│   ├── core.md                default skill template
│   └── methodology-debate-convener/
│       └── SKILL.md           full 7-phase runbook (loaded at Stage 4)
└── tools/
    └── manifest.yaml          no MCP/custom tools — uses host run_debate
```

## Upstream source

This talent was extracted from the OneManCompany AutoResearch pipeline at
<https://github.com/Memento-Teams/Memento-Research>. The
`methodology-debate-convener/SKILL.md` runbook is identical to that repo's
`src/onemancompany/talent_market/talents/methodology-designer/skills/`
version.

## License

See [LICENSE](./LICENSE).
