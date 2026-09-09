---
description: Review a baseline report or study for indicator coverage, sampling methodology, disaggregation, measurement consistency, and endline comparability
argument-hint: "[paste your baseline report or describe the study methodology and findings]"
---

# /baseline-report-review -- Baseline Report Review

Review a baseline report against M&E methodology standards. Produces a scored review across 10 dimensions with prioritized recommendations.

## Invocation

```
/me-review:baseline-report-review

[paste your baseline report here]
```

## Workflow

### Step 1: Accept Input

Accept the baseline report in any of these formats:
- **Full report:** Complete baseline study with methodology, findings, and annexes
- **Data summary:** Indicator values table without methodology
- **Methodology section:** Sampling and data collection approach only
- **Narrative description:** User describes the baseline study
- **Partial draft:** Incomplete report for early-stage feedback

If invoked with `$ARGUMENTS`, treat that as the report content to review.

### Step 2: Classify the Document

Identify the document type (Full baseline report, Data summary, Rapid assessment, Secondary data compilation, or Partial Draft). State classification at the top and adjust expectations:
- **Data summaries:** Score indicator coverage; flag missing methodology
- **Rapid assessments:** Calibrate expectations for speed; focus on coverage and usability
- **Partial Drafts:** Note gaps as "needs development"

### Step 3: Handle Non-Standard Input

**Narrative description:** Summarize understanding of each section, then review. Flag unaddressed sections as "not confirmed present."

**Data tables only:** Score Sections 1, 3, 4 in full. Note methodology sections cannot be assessed.

### Step 4: Conduct 10-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **Indicator Coverage** -- Baseline values for all key indicators?
2. **Sampling Methodology** -- Representative? Sample size justified? DEFF?
3. **Disaggregation** -- Sex, age, geography, disability?
4. **Measurement Consistency** -- Replicable at endline?
5. **Comparison Group** -- Established? Equivalence tested? (N/A if not planned)
6. **Data Quality** -- Response rates? Missing data? Cleaning documented?
7. **Context Analysis** -- Relevant factors documented?
8. **Target Validation** -- Baseline vs. planned targets assessed?
9. **Ethical Compliance** -- IRB, consent, data protection?
10. **Report Usability** -- Well-organized? Summary table? Annexes?

### Step 5: Calculate Overall Rating

- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

**Note:** A FAIL in Indicator Coverage or Sampling Methodology automatically triggers Major Issues.

### Step 6: Generate Output

```
## Baseline Report Review Summary

**Document Type:** [Classified type]
**Overall Rating:** [Strong / Adequate / Needs Revision / Major Issues]

**Score Summary:**
| Section | Score |
|---------|-------|
| 1. Indicator Coverage | PASS / PARTIAL / FAIL |
| 2. Sampling Methodology | PASS / PARTIAL / FAIL |
| 3. Disaggregation | PASS / PARTIAL / FAIL |
| 4. Measurement Consistency | PASS / PARTIAL / FAIL |
| 5. Comparison Group | PASS / PARTIAL / FAIL / N/A |
| 6. Data Quality | PASS / PARTIAL / FAIL |
| 7. Context Analysis | PASS / PARTIAL / FAIL |
| 8. Target Validation | PASS / PARTIAL / FAIL |
| 9. Ethical Compliance | PASS / PARTIAL / FAIL |
| 10. Report Usability | PASS / PARTIAL / FAIL |

---

## Priority Recommendations

[3-5 highest-priority issues, ordered by severity.]

1. **[Section Name]:** [Specific finding] -- [Specific recommendation]
2. ...

---

## Detailed Findings

### 1. Indicator Coverage -- [PASS / PARTIAL / FAIL]
[Findings]

### 2. Sampling Methodology -- [PASS / PARTIAL / FAIL]
[Findings]

### 3. Disaggregation -- [PASS / PARTIAL / FAIL]
[Findings]

### 4. Measurement Consistency -- [PASS / PARTIAL / FAIL]
[Findings]

### 5. Comparison Group -- [PASS / PARTIAL / FAIL / N/A]
[Findings]

### 6. Data Quality -- [PASS / PARTIAL / FAIL]
[Findings]

### 7. Context Analysis -- [PASS / PARTIAL / FAIL]
[Findings]

### 8. Target Validation -- [PASS / PARTIAL / FAIL]
[Findings]

### 9. Ethical Compliance -- [PASS / PARTIAL / FAIL]
[Findings]

### 10. Report Usability -- [PASS / PARTIAL / FAIL]
[Findings]

---

## Design Flaw Flags
[List any common design flaws detected]
```

## Output Rules

- Frame every critical issue in terms of: "Will this compromise the endline comparison?"
- Distinguish between methodological flaws (wrong sampling) and documentation gaps (valid findings, poorly organized)
- For rapid-response programs, calibrate expectations appropriately
- When recommending target revisions, provide specific suggested values, not just "revise targets"
- For PARTIAL scores, state exactly what is present and what is missing
