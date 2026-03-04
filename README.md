# M&E Review

Professional monitoring, evaluation, accountability and learning (MEAL) skills for Claude.

Paste a logframe, M&E plan, survey, evaluation TOR, or indicator list and get a structured quality review in seconds.

Built by [MEStudio](https://monitoringevaluationstudio.com).

## What It Does

| Skill | Use It When You Have... |
|-------|------------------------|
| `/me-review:logframe-review` | A logframe or results framework to check |
| `/me-review:indicator-quality` | A list of indicators to score against SMART criteria |
| `/me-review:tor-review` | An evaluation TOR or SOW to review |
| `/me-review:me-plan-review` | An M&E plan, MEAL plan, PMP, or MEL plan to assess |
| `/me-review:evaluation-report-review` | A final evaluation report to assess for quality, evidence, and limitations |
| `/me-review:survey-review` | A survey, questionnaire, KII guide, or data collection instrument to check |

Each skill produces a scored review with section-by-section ratings (PASS / PARTIAL / FAIL), a summary verdict, and prioritized recommendations.

## Installation

### Claude Desktop (Mac and Windows)

1. Open Claude Desktop
2. Go to **Settings → Extensions**
3. Click **Add from GitHub** and enter: `monitoringevaluationstudio/me-review`
4. Click **Install**

That is it. No downloads, no coding, no setup.

### Claude Code (CLI)

```bash
/install-plugin monitoringevaluationstudio/me-review
```

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

## License

MIT — Copyright (c) 2026 MEStudio
