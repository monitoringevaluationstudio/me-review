---
description: Review a DQA report, DQA plan, or data quality audit for scope, verification rigor, VIPRT coverage, systems assessment, and action plan quality
argument-hint: "[paste your DQA report or describe the data quality assessment]"
---

# /data-quality-review -- Data Quality Assessment Review

Review a data quality assessment against M&E methodology standards. Produces a scored review across 8 dimensions with prioritized recommendations.

## Invocation

```
/me-review:data-quality-review

[paste your DQA report here]
```

## Workflow

### Step 1: Accept Input

Accept the DQA in any of these formats:
- **Full DQA report:** Complete assessment with VIPRT, verification, action plan
- **DQA plan:** Planned assessment methodology and scope
- **Verification report:** Focused on verification ratios
- **Routine check:** Lighter-touch periodic data quality check
- **Narrative description:** User describes the assessment

If invoked with `$ARGUMENTS`, treat that as the DQA content to review.

### Step 2: Classify the Document

Identify the document type. Adjust expectations:
- **DQA plans:** Review methodology and scope; skip verification dimensions (they haven't happened yet)
- **Verification reports:** Assess rigor; flag missing VIPRT dimensions
- **Routine checks:** Calibrate expectations for lighter scope

### Step 3: Handle Non-Standard Input

**Narrative description:** Summarize understanding, then review. Flag unaddressed areas as "not confirmed present."

### Step 4: Conduct 8-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **Scope Adequacy** -- Key indicators covered? High-risk prioritized?
2. **Verification Rigor** -- Source documents traced? Ratios calculated?
3. **VIPRT Coverage** -- All 5 dimensions assessed with evidence?
4. **Systems Assessment** -- Data flow examined? Capacity assessed?
5. **Action Plan Quality** -- Specific actions? Assigned? Timeline?
6. **Independence** -- Assessor different from data collector?
7. **Follow-up on Prior DQA** -- Previous recommendations tracked? (N/A if first)
8. **Documentation** -- Tools, checklists, site visit records complete?

### Step 5: Calculate Overall Rating

- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Improvement:** 1 FAIL, or 3+ PARTIAL
- **Serious Concerns:** 2+ FAIL

### Step 6: Generate Output

```
## Data Quality Assessment Review Summary

**Document Type:** [Classified type]
**Overall Rating:** [Strong / Adequate / Needs Improvement / Serious Concerns]

**Score Summary:**
| Section | Score |
|---------|-------|
| 1. Scope Adequacy | PASS / PARTIAL / FAIL |
| 2. Verification Rigor | PASS / PARTIAL / FAIL |
| 3. VIPRT Coverage | PASS / PARTIAL / FAIL |
| 4. Systems Assessment | PASS / PARTIAL / FAIL |
| 5. Action Plan Quality | PASS / PARTIAL / FAIL |
| 6. Independence | PASS / PARTIAL / FAIL |
| 7. Follow-up on Prior DQA | PASS / PARTIAL / FAIL / N/A |
| 8. Documentation | PASS / PARTIAL / FAIL |

---

## VIPRT Summary (if assessed)

| Dimension | Finding | Concern Level |
|-----------|---------|---------------|
| Validity | [summary] | [None / Minor / Major] |
| Integrity | [summary] | [None / Minor / Major] |
| Precision | [summary] | [None / Minor / Major] |
| Reliability | [summary] | [None / Minor / Major] |
| Timeliness | [summary] | [None / Minor / Major] |

---

## Priority Recommendations

1. **[Section Name]:** [Specific finding] -- [Specific recommendation]
2. ...

---

## Detailed Findings

### 1. Scope Adequacy -- [PASS / PARTIAL / FAIL]
[Findings]
...
### 8. Documentation -- [PASS / PARTIAL / FAIL]
[Findings]

---

## Design Flaw Flags
[List any common design flaws detected]
```

## Output Rules

- Weight action plan quality heavily: a well-conducted assessment with no follow-through is still inadequate
- Verification ratios are the most concrete DQA output; always assess whether they are present and reasonable
- Distinguish between DQA plans (prospective) and DQA reports (retrospective) in recommendations
- For first-year DQAs, calibrate expectations but still flag critical gaps
