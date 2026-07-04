<p align="right">
  <a href="./README.md"><kbd>中文</kbd></a>
  <a href="./README.en.md"><kbd>English</kbd></a>
</p>

# Research Dossier Workflow

A Codex Skill for turning an industry topic, article, market question, policy issue, company set, investment theme, or strategy question into two paired outputs:

1. **A source-backed research dossier** that preserves the question tree, evidence, sources, gaps, counter-evidence, and action boundaries.
2. **A research report draft** built from the dossier, with uncertainty and open verification points kept visible.

The skill is designed for research scenarios where claims need to stay traceable to sources, evidence must be reviewable, and recommendations should not outrun the facts.

## What It Produces

By default, the skill produces both artifacts:

- **Research dossier**: decision question, research questions, evidence gap table, source ledger, structured extraction, insight candidates, action boundary, and next verification steps.
- **Research report draft**: title and scope, executive summary, context, evidence-backed analysis, insight boxes, risks and limitations, recommendations or next steps, and sources.

## Install

Install with the Codex Skill installer:

```bash
python3 ~/.codex/skills/.system/skill-installer/scripts/install-skill-from-github.py \
  --repo smilelida/research-dossier-workflow \
  --path skills/research-dossier-workflow
```

Then restart Codex so the new skill is loaded.

Manual install:

```bash
git clone https://github.com/smilelida/research-dossier-workflow.git
mkdir -p ~/.codex/skills
cp -R research-dossier-workflow/skills/research-dossier-workflow ~/.codex/skills/
```

## Usage

```text
Use $research-dossier-workflow.

Topic: [topic]
Audience: [who will read/use this]
Decision: [what they need to decide]
Time horizon: [now/90 days/1 year/3-5 years]
Known materials: [links, files, notes, transcripts]
Privacy level: [public/internal/confidential]

Produce both:
1. a research dossier with research questions, evidence gaps, source ledger, structured extraction, insight candidates with counter-evidence, action boundary, and next verification steps;
2. a research report draft with executive summary, context, evidence-backed analysis, risks, next steps, and sources.
```

Short form:

```text
Use $research-dossier-workflow to turn [topic] into a source-backed dossier and research report draft.
```

## Privacy Posture

This public version contains no private workflow details, client identifiers, local absolute paths, credentials, tokens, hidden memory, or workspace-specific assumptions.

The skill also instructs the model to sanitize public-facing outputs by removing private names, internal project names, local paths, account details, credentials, private client details, and sensitive examples.

## Repository Layout

```text
.
├── README.md
├── README.en.md
├── LICENSE
└── skills/
    └── research-dossier-workflow/
        ├── SKILL.md
        └── agents/
            └── openai.yaml
```

## License

MIT
