# M&E Review

[![Version](https://img.shields.io/badge/version-1.4.0-0B4F6C)](https://github.com/monitoringevaluationstudio/me-review/releases)
[![License](https://img.shields.io/badge/license-MIT-3AA6A0)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-compatible-D97706)](https://code.claude.com/docs/en/plugins)

Professional monitoring, evaluation, accountability and learning (MEAL) skills for Claude.

Paste a logframe, theory of change, M&E plan, survey, evaluation TOR, sampling plan, baseline report, progress report, proposal, or indicator list and get a structured quality review in seconds.

Built by [M&E Studio](https://www.monitoringevaluationstudio.com/plugins).

**New in 1.4.0:** the plugin now ships as its own marketplace, so installation is two commands (see below). Each review is a single self-contained skill.

**New in 1.3.0:** six additional reviews covering theories of change, proposal M&E sections, sampling plans, data quality assessments, baseline reports and progress reports. Twelve reviews in total.

## What It Does

| Skill | Use It When You Have... |
|-------|------------------------|
| `/me-review:logframe-review` | A logframe or results framework to check for logic gaps, weak indicators and missing assumptions |
| `/me-review:theory-of-change-review` | A theory of change, causal pathway or results chain to check for logical coherence and assumption quality |
| `/me-review:indicator-quality` | A list of indicators to score against SMART and CREAM criteria |
| `/me-review:me-plan-review` | An M&E plan, MEAL plan, PMP or MEL plan to assess for completeness and feasibility |
| `/me-review:proposal-me-review` | The M&E section of a proposal, grant application or concept note |
| `/me-review:tor-review` | An evaluation TOR or SOW to review for methodological rigor, scope and budget realism |
| `/me-review:survey-review` | A survey, questionnaire, KII guide or FGD guide to check for design quality and ethics |
| `/me-review:sampling-plan-review` | A sampling plan, sample size calculation or sampling frame to check for method appropriateness |
| `/me-review:baseline-report-review` | A baseline report or pre-intervention study to check for indicator coverage and target validation |
| `/me-review:progress-report-review` | A quarterly, annual or donor progress report to check for data plausibility and variance explanation |
| `/me-review:data-quality-review` | A DQA report, data quality audit or verification report to check for VIPRT coverage and rigor |
| `/me-review:evaluation-report-review` | A final evaluation report to assess for quality, evidence anchoring and limitations |

Each skill produces a scored review with section-by-section ratings (PASS / PARTIAL / FAIL), a summary verdict, and prioritized recommendations.

## Installation

Two commands. This repository is its own plugin marketplace, so you add it once and then install from it.

```
/plugin marketplace add monitoringevaluationstudio/me-review
/plugin install me-review@me-review
```

Run these inside Claude Code. If the install summary says `Run /reload-plugins to activate.`, run that too.

To check it worked, type `/me-review:` and you should see all twelve reviews listed.

Claude Desktop users can install the same plugin through the plugin browser in **Settings**.

## How to Use

Type a slash command, then paste your document:

**Logframe review:**
```
/me-review:logframe-review

Objective: Improved health outcomes for rural women
Output 1: 500 health workers trained
Output 2: 12 health facilities upgraded
Indicator: Number of women accessing services (target: 10,000)
```

**Theory of change review:**
```
/me-review:theory-of-change-review

[paste your theory of change, causal pathway, or results chain here]
```

**Indicator quality check:**
```
/me-review:indicator-quality

1. Number of health workers trained (target: 500)
2. % of facilities with adequate supplies (baseline: 42%)
3. Women's empowerment improved
```

**Evaluation TOR review:**
```
/me-review:tor-review

[paste your evaluation TOR here]
```

**M&E plan review:**
```
/me-review:me-plan-review

[paste your M&E plan, MEL plan, PMP, or MEAL plan here]
```

**Sampling plan review:**
```
/me-review:sampling-plan-review

Population: 12,400 households across 3 districts
Method: Two-stage cluster sampling, 40 clusters of 15 households
Sample size: 600, calculated for 5% margin of error at 95% confidence
Disaggregation required: sex of household head, district
```

**Evaluation report review:**
```
/me-review:evaluation-report-review

FINDINGS

Finding 1: Student learning improved 23% on average (treatment: 65%, control: 53%)
- Evidence: Pre/post learning assessments in 60 schools, 4,800 students
- Limitations: Comparison group non-randomly selected; causality estimates may reflect contextual differences

Finding 2: Teacher practice improved significantly (78% competency-based teaching in treatment vs. 12% in control)
- Evidence: Classroom observations using validated rubric, 240 observations across sites
- Limitation: Self-selection of trained teachers may bias estimates

RECOMMENDATIONS

Priority 1: Scale to 200 additional schools by 2025 ($1.86M investment)
Priority 2: Establish peer learning networks to sustain practice changes
Priority 3: Conduct 2-year follow-up to verify learning gains persist
```

**Survey review:**
```
/me-review:survey-review

[paste your survey, questionnaire, or KII guide here]
```

Claude will review the document and return a structured report.

You can also just paste a document without typing a command. Claude will detect what it is and apply the right review automatically.

## More free M&E resources

This plugin is one part of a free toolkit for M&E practitioners.

| Resource | What it is |
|---|---|
| [AI prompt library](https://www.monitoringevaluationstudio.com/ai-for-me/prompts) | Task-specific prompts for M&E work, in English, Spanish and French |
| [Free M&E tools](https://www.monitoringevaluationstudio.com/tools) | Sampling calculator, DQA scorecard, SMART indicator checker, method selector, evaluation readiness check |
| [M&E reference library](https://www.monitoringevaluationstudio.com/resources/reference) | Plain-language entries on M&E methods, terms and comparisons |
| [Method guides](https://www.monitoringevaluationstudio.com/guides) | Step-through guides for planning and running evaluations |
| [Plugin page](https://www.monitoringevaluationstudio.com/plugins) | Installation help and what each skill checks |

## License

MIT License. Copyright (c) 2026 MEStudio
