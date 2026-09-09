---
description: Review a sampling plan, sample size calculation, or survey methodology for method appropriateness, justification, frame quality, and feasibility
argument-hint: "[paste your sampling plan or describe the sampling methodology]"
---

# /sampling-plan-review -- Sampling Plan Review

Review a sampling plan against M&E methodology standards. Produces a scored review across 7 dimensions with independent sample size verification.

## Invocation

```
/me-review:sampling-plan-review

[paste your sampling plan here]
```

## Workflow

### Step 1: Accept Input

Accept the sampling plan in any of these formats:
- **Full plan:** Complete sampling methodology document
- **Methodology section:** Sampling approach within a larger document
- **Sample size calculation:** Parameters and formula only
- **Narrative description:** User describes the sampling approach
- **Qualitative sampling:** Purposive strategy for qualitative research

If invoked with `$ARGUMENTS`, treat that as the plan content to review.

### Step 2: Classify the Document

Identify the document type. Adjust expectations:
- **Qualitative sampling:** Do not apply sample size formulas; assess selection criteria, diversity, saturation strategy
- **Embedded methodology:** Extract sampling content; assess standalone
- **Brief/outline:** Flag missing elements; assess what is present

### Step 3: Handle Non-Standard Input

**Sample size calculation only:** Verify the calculation; note that other dimensions cannot be assessed.

**Narrative description:** Summarize understanding, then review.

### Step 4: Conduct 7-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **Method Appropriateness** -- Does the method match the research question?
2. **Sample Size Justification** -- Calculation complete? Parameters documented?
3. **Sampling Frame Quality** -- Frame defined, accessible, current?
4. **Selection Procedure** -- Step-by-step? Replicable?
5. **Disaggregation Feasibility** -- Sample supports required subgroup analyses?
6. **Practical Feasibility** -- Achievable within time, budget, access?
7. **Limitations Transparency** -- Stated honestly? Mitigations proposed?

### Step 4a: Verify Sample Size Calculation (if provided)

If a sample size calculation is provided, verify independently:
1. Identify the formula used
2. Check each parameter
3. Recalculate
4. Compare claimed vs. recalculated
5. Check non-response buffer

Present verification result as part of Section 2 findings.

### Step 5: Calculate Overall Rating

- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

**Note:** A FAIL in Method Appropriateness or Sample Size Justification automatically triggers Major Issues.

### Step 6: Generate Output

```
## Sampling Plan Review Summary

**Document Type:** [Classified type]
**Sampling Method Identified:** [SRS / Stratified / Cluster / etc.]
**Overall Rating:** [Strong / Adequate / Needs Revision / Major Issues]

**Score Summary:**
| Section | Score |
|---------|-------|
| 1. Method Appropriateness | PASS / PARTIAL / FAIL |
| 2. Sample Size Justification | PASS / PARTIAL / FAIL |
| 3. Sampling Frame Quality | PASS / PARTIAL / FAIL |
| 4. Selection Procedure | PASS / PARTIAL / FAIL |
| 5. Disaggregation Feasibility | PASS / PARTIAL / FAIL |
| 6. Practical Feasibility | PASS / PARTIAL / FAIL |
| 7. Limitations Transparency | PASS / PARTIAL / FAIL |

---

## Sample Size Verification (if calculation provided)

| Parameter | Stated | Assessment |
|-----------|--------|------------|
| Confidence level | [value] | [OK / Missing / Non-standard] |
| Margin of error | [value] | [OK / Missing] |
| Expected proportion | [value] | [OK / Missing] |
| Design effect | [value] | [OK / Missing / Underestimated] |
| Non-response buffer | [value] | [OK / Missing] |
| **Calculated sample** | [N] | [Confirmed / Discrepancy of X%] |

---

## Priority Recommendations

1. **[Section Name]:** [Specific finding] -- [Specific recommendation]
2. ...

---

## Detailed Findings

### 1. Method Appropriateness -- [PASS / PARTIAL / FAIL]
[Findings]
...
### 7. Limitations Transparency -- [PASS / PARTIAL / FAIL]
[Findings]

---

## Design Flaw Flags
[List any common design flaws detected]
```

## Output Rules

- Be precise with numbers in sample size verification; rounding differences (<5%) are not discrepancies
- "Purposive sampling" is valid for qualitative but cannot support statistical generalization
- Cluster designs without DEFF are always a Critical issue
- "Random" without a specified procedure is a common problem worth flagging
- For endline plans, flag inconsistency with baseline methodology
