---
description: Review a progress report, quarterly/annual report, or donor report for indicator coverage, data plausibility, narrative-data alignment, and variance explanation
argument-hint: "[paste your progress report or describe the report structure and key indicators]"
---

# /progress-report-review -- Progress Report Review

Review a progress report against M&E reporting standards. Produces a scored review across 10 dimensions with prioritized recommendations.

## Invocation

```
/me-review:progress-report-review

[paste your progress report here]
```

## Workflow

### Step 1: Accept Input

Accept the progress report in any of these formats:
- **Full report:** Complete progress report with indicator table, narrative, financial summary
- **Indicator table only:** Achievement data without narrative
- **Narrative only:** Program narrative without indicator table
- **Narrative description:** User describes the report content
- **Partial draft:** Incomplete report for early-stage feedback

If invoked with `$ARGUMENTS`, treat that as the report content to review.

### Step 2: Classify the Document

Identify the report type (Quarterly, Semi-annual, Annual, Final/Completion, or Donor-specific format). State classification and adjust expectations:
- **Quarterly:** Output indicators sufficient; outcome indicators optional
- **Annual/Final:** All indicators expected; full narrative and lessons required
- **Donor-specific:** Check format compliance alongside quality

### Step 3: Handle Non-Standard Input

**Indicator table only:** Score Sections 1-4 in full. Flag that narrative sections cannot be assessed.

**Narrative only:** Score Sections 5-9. Flag that data plausibility cannot be verified without indicator table.

### Step 4: Conduct 10-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **Indicator Coverage** -- All expected indicators reported?
2. **Data Completeness** -- Baseline, target, actual, source, achievement % for each?
3. **Data Plausibility** -- Values mathematically consistent? Contextually realistic?
4. **Disaggregation** -- Sex, age, geography as required?
5. **Narrative-Data Alignment** -- Narrative matches data? Both successes and shortfalls?
6. **Variance Explanation** -- Off-track indicators explained? Corrective actions?
7. **Activity Progress** -- Status clear? Delays explained?
8. **Financial Alignment** -- Burn rate reasonable? Financial matches programmatic?
9. **Lessons and Adaptation** -- Specific? Actionable? Connected to decisions?
10. **Internal Consistency** -- Cross-section checks pass?

### Step 5: Calculate Overall Rating

- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

**Note:** A FAIL in Data Plausibility automatically triggers Major Issues.

### Step 6: Generate Output

```
## Progress Report Review Summary

**Document Type:** [Report type]
**Reporting Period:** [If stated]
**Overall Rating:** [Strong / Adequate / Needs Revision / Major Issues]

**Score Summary:**
| Section | Score |
|---------|-------|
| 1. Indicator Coverage | PASS / PARTIAL / FAIL |
| 2. Data Completeness | PASS / PARTIAL / FAIL |
| 3. Data Plausibility | PASS / PARTIAL / FAIL |
| 4. Disaggregation | PASS / PARTIAL / FAIL |
| 5. Narrative-Data Alignment | PASS / PARTIAL / FAIL |
| 6. Variance Explanation | PASS / PARTIAL / FAIL |
| 7. Activity Progress | PASS / PARTIAL / FAIL |
| 8. Financial Alignment | PASS / PARTIAL / FAIL |
| 9. Lessons and Adaptation | PASS / PARTIAL / FAIL |
| 10. Internal Consistency | PASS / PARTIAL / FAIL |

---

## Priority Recommendations

1. **[Section Name]:** [Specific finding] -- [Specific recommendation]
2. ...

---

## Detailed Findings

### 1. Indicator Coverage -- [PASS / PARTIAL / FAIL]
[Findings]
...
### 10. Internal Consistency -- [PASS / PARTIAL / FAIL]
[Findings: specific cross-section contradictions]

---

## Design Flaw Flags
[List any common design flaws detected]
```

## Output Rules

- Lead with specific data issues, not generic quality labels
- When identifying plausibility concerns, state the specific numbers that are problematic
- Distinguish between data errors (wrong) and reporting gaps (missing)
- For PARTIAL scores, state exactly what is present and what is missing
- If donor-specific format, note compliance issues alongside quality issues
- Do not recommend the same corrective action more than once across sections
