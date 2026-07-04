---
name: research-dossier-workflow
description: Use when turning an industry topic, article, market question, policy issue, company set, investment theme, or strategy question into a source-backed research dossier and research report draft. Also use when the user asks for 研报, industry research, evidence ledger, source ledger, decision memo, market analysis, consulting-style research, insight generation, counter-evidence, or a report that preserves citations, uncertainty, and action boundaries.
---

# Research Dossier Workflow

## Overview

Produce two paired outputs:

1. **Research dossier** - the evidence base, source ledger, gaps, hypotheses, counter-evidence, and action boundaries.
2. **Research report draft** - a readable first draft built from the dossier, with limitations and open questions preserved.

Treat AI as a research assistant, not the signing analyst. A report draft is useful only when readers can trace the claims behind it.

## Privacy And Public-Safety Rules

Before producing or publishing any output, remove private context that is not needed for the research question:

- No personal names, local usernames, local absolute paths, private project names, internal account details, credentials, tokens, or private client identifiers.
- No hidden conversation history, internal memory, or workspace-specific conventions unless the user explicitly asks for a private internal artifact.
- For public artifacts, anonymize examples and replace local paths with generic placeholders such as `~/path/to/skill`.
- Keep sensitive facts out of examples. Use public, generic, or synthetic examples.

## First Response

Start by identifying:

- Audience: who will use the output.
- Decision: what they need to decide after reading.
- Horizon: immediate, 90 days, 1 year, or 3-5 years.
- Risk level: ordinary, financial/investment, legal/compliance, medical/scientific, client-sensitive, or reputational.
- Output need: dossier plus report draft by default, or only one of them if the user says so.

If the decision frame is unclear, infer a practical frame and state the assumption. Ask only when a wrong frame would make the work unsafe or useless.

## Default Deliverable

Unless the user explicitly asks for only one artifact, produce both parts.

### Part A: Research Dossier

Include these sections:

1. **Decision Question** - one sentence naming the decision and audience.
2. **Research Questions** - 3-5 questions that must be answered.
3. **Evidence Gap Table** - required facts, preferred sources, current status, next step.
4. **Source Ledger** - source name, link/path, publication date, data period, credibility, limitations.
5. **Structured Extraction** - relevant facts grouped by market, product, company, policy, technology, economics, risk, or other useful dimensions.
6. **Insight Candidates** - claim, evidence, reasoning, counter-evidence, confidence, and action implication.
7. **Action Boundary** - what can be done now, what must wait, and what must not be inferred.
8. **Next Verification Steps** - the smallest source checks needed to improve confidence.

Use Markdown tables for comparison. Label unsupported claims as `Needs verification` or `Low confidence`.

### Part B: Research Report Draft

Write a readable report draft after the dossier. If evidence is incomplete, keep the report as a draft and label open points clearly.

Use this structure:

1. **Title And Scope** - topic, audience, horizon, and what the report does not cover.
2. **Executive Summary** - 3-5 findings tied to evidence.
3. **Context** - why the topic matters now.
4. **Evidence-Backed Analysis** - sections organized by the decision logic, not by random source order.
5. **Insight Boxes** - non-obvious takeaways with evidence and counter-evidence.
6. **Risks And Limitations** - what could invalidate the conclusions.
7. **Recommendations Or Next Steps** - concrete, bounded actions and prerequisites.
8. **Sources** - cited sources from the source ledger.

For high-stakes topics, state that the report is for research support and does not replace qualified professional judgment.

## Workflow

### 1. Frame The Decision

Reframe broad prompts into:

```text
For [audience], decide [decision] about [topic] by [time horizon], using evidence about [key dimensions].
```

Avoid starting from "write a report about X" without a decision frame.

### 2. Build The Question Tree

Create 3-5 core questions. For each, list:

- What would change the decision.
- What data or examples are needed.
- Which sources are most authoritative.
- What would falsify the likely conclusion.

Prefer concrete questions over generic sections. Bad: "market analysis". Better: "Is demand growing fast enough to justify entering within 12 months?"

### 3. Gather And Rank Sources

Use current sources when facts may have changed. Prefer primary or high-authority sources:

- Market and macro: official statistics, regulator publications, recognized research firms.
- Company: annual reports, prospectuses, investor presentations, exchange filings.
- Technical: papers, patents, standards, vendor documentation, expert interviews.
- Policy: government and regulator sites, original policy documents, recognized legal or policy analysis.
- Product or customer evidence: public case studies, verified interviews, credible user data, public procurement or contract records.

Every important number needs source, date, period, and scope. If sources disagree, show the range and explain likely scope differences.

### 4. Extract Before Interpreting

Separate raw facts from interpretation:

```markdown
| Fact | Source | Date/period | Scope | Confidence | Notes |
|---|---|---|---|---|---|
```

Then cluster facts into the few categories that matter for the decision. Do not dump every interesting detail.

### 5. Generate Insight Candidates

An insight is only useful if it changes action or understanding. Require:

```markdown
| Claim | Evidence | Reasoning | Counter-evidence | Confidence | Action implication |
|---|---|---|---|---|---|
```

For contrarian claims, require at least two independent evidence lines or label the claim as a hypothesis. Do not manufacture contrarian takes just to sound sharp.

### 6. Run The Review Gate

Before finalizing the report draft, check:

- Does every key claim have a source or a visible `Needs verification` label?
- Are facts, inferences, judgments, and actions separated?
- Are source dates and data periods visible?
- Are counterarguments or disconfirming evidence included?
- Can the user defend the main conclusion if challenged?
- Has private or identifying information been removed when the artifact is public-facing?

If the gate fails, still provide the dossier and a clearly labeled draft, but list the missing evidence before the recommendations.

### 7. Draft The Report

Write the report from the dossier. Keep claims specific, avoid filler, and preserve uncertainty. Do not upgrade weak evidence into confident prose.

Avoid weak phrases like:

- "with the development of..."
- "AI is the future"
- "it may be worth paying attention to"
- "industry prospects are broad"

Replace them with source-backed statements about scope, magnitude, timing, evidence, and uncertainty.

## Adaptation Patterns

### Industry Or Market Report

Use these dimensions:

- Definition and scope.
- Market size, growth, and demand drivers.
- Value chain and profit pools.
- Product or technology routes.
- Competitive landscape.
- Policy and regulation.
- Trends, opportunities, and risks.
- Reader-specific next steps.

### Company Or Competitor Research

Use these dimensions:

- Business model and revenue quality.
- Product strength and differentiation.
- Customer base and go-to-market motion.
- Financial performance and cash flow.
- Competitive position.
- Risks, dependencies, and open questions.

### Policy Or Strategy Memo

Use these dimensions:

- Policy text and effective dates.
- Affected stakeholders.
- Required behavior changes.
- Compliance or operational implications.
- Scenario analysis and next actions.

### Financial Or Investment Research

Use these rules:

- Separate observation, thesis, evidence, risk, and action.
- Do not convert a research report into a trade recommendation unless explicitly requested and sufficient evidence exists.
- Mark stale market data, uncertain estimates, and missing filings.
- Preserve valuation and price-data gaps as blockers.

## Prompt Templates

### Build Dossier And Report Draft

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

### Convert Existing Dossier To Report Draft

```text
Use the existing dossier. Run the review gate first. Keep unsupported claims as Needs verification. Then write a concise research report draft for [audience] with findings, analysis, risks, recommendations or next steps, and sources.
```

### Sanitize For Public Release

```text
Sanitize this dossier/report for public release. Remove private names, local paths, internal project names, credentials, private client details, and workspace-specific assumptions. Replace sensitive examples with generic or public examples. Keep the research method intact.
```

## Common Mistakes

- Stopping after the dossier when the user expects a report draft.
- Starting with a polished report before evidence exists.
- Treating AI-generated source names as verified sources.
- Hiding uncertainty inside confident prose.
- Calling a generic trend an insight.
- Creating contrarian claims without counter-evidence checks.
- Mixing facts, interpretation, and suggested action in one paragraph.
- Publishing private local paths, personal context, or internal client details.

## Completion Standard

A good output lets the user answer:

- What decision is this for?
- Which claims are sourced?
- Which claims are hypotheses?
- What evidence would change the conclusion?
- What can be done now, and what must wait?
- What does the readable report draft say?
- Is the artifact safe for its declared privacy level?
