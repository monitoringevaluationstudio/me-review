---
description: Review the M&E section of a proposal, grant application, or concept note for approach quality, indicator selection, evaluation planning, budget, and staffing
argument-hint: "[paste your proposal's M&E section or describe the M&E approach]"
---

# /proposal-me-review -- Proposal M&E Section Review

Review the M&E section of a proposal against professional standards. Produces a scored review across 9 dimensions with prioritized recommendations.

## Invocation

```
/me-review:proposal-me-review

[paste your proposal's M&E section here]
```

## Workflow

### Step 1: Accept Input

Accept the M&E section in any of these formats:
- **Full M&E section:** Complete M&E section from a proposal
- **M&E annex:** Standalone M&E plan submitted as proposal annex
- **Concept note M&E:** Brief M&E approach from a concept note
- **Narrative description:** User describes the M&E approach
- **Partial draft:** Incomplete section for early-stage feedback

If invoked with `$ARGUMENTS`, treat that as the M&E section content to review.

### Step 2: Classify the Document

Identify the document type (Full proposal M&E section, Concept note, Expression of interest, Standalone annex, or Partial Draft). Adjust expectations:
- **Concept notes:** Assess only components 1-3; note others are intentionally deferred
- **Expressions of interest:** Minimal review; note what to develop
- **Standalone annexes:** Full review; may overlap with M&E plan review

### Step 3: Handle Non-Standard Input

**Narrative description:** Summarize understanding of each component, then review. Flag unaddressed components as "not confirmed present."

**Logframe only:** Assess component 2 (Results Framework) and partially component 3 (Indicators). Note other components cannot be assessed.

### Step 4: Conduct 9-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **M&E Approach** -- Specific to program? Methodology named? Not boilerplate?
2. **Results Framework** -- Embedded or referenced? Consistent with narrative?
3. **Key Indicators** -- Outcome-level present? Match logframe? Standards used?
4. **Data Collection Methods** -- Linked to indicators? Rationale? Feasible?
5. **Evaluation Plan** -- Baseline/midterm/endline planned? Budget? Independence?
6. **Data Quality** -- DQA described? Verification? Beyond generic statements?
7. **Learning and Adaptation** -- Feedback mechanisms? Frequency? Action process?
8. **M&E Budget** -- Visible? Proportionate? All categories covered?
9. **M&E Staffing** -- Dedicated positions? Proportionate? LOE specified?

### Step 5: Calculate Overall Rating

- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

### Step 6: Generate Output

```
## Proposal M&E Section Review Summary

**Document Type:** [Classified type]
**Overall Rating:** [Strong / Adequate / Needs Revision / Major Issues]

**Score Summary:**
| Section | Score |
|---------|-------|
| 1. M&E Approach | PASS / PARTIAL / FAIL |
| 2. Results Framework | PASS / PARTIAL / FAIL |
| 3. Key Indicators | PASS / PARTIAL / FAIL |
| 4. Data Collection Methods | PASS / PARTIAL / FAIL |
| 5. Evaluation Plan | PASS / PARTIAL / FAIL |
| 6. Data Quality | PASS / PARTIAL / FAIL |
| 7. Learning and Adaptation | PASS / PARTIAL / FAIL |
| 8. M&E Budget | PASS / PARTIAL / FAIL |
| 9. M&E Staffing | PASS / PARTIAL / FAIL |

---

## Priority Recommendations

[3-5 highest-priority issues, ordered by severity.]

1. **[Section Name]:** [Specific finding] -- [Specific recommendation]
2. ...

---

## Detailed Findings

### 1. M&E Approach -- [PASS / PARTIAL / FAIL]
[Findings]
...
### 9. M&E Staffing -- [PASS / PARTIAL / FAIL]
[Findings]

---

## Design Flaw Flags
[List any common design flaws detected]
```

## Output Rules

- Frame issues in competitive terms where applicable ("This would likely weaken the proposal's score because...")
- Distinguish between donor-specific requirements and general best practice
- For concept notes, note "This component should be developed in the full proposal" rather than scoring FAIL
- For PARTIAL scores, state exactly what is present and what is missing
- If the user mentions a specific donor, apply that donor's M&E patterns from the skill
- Do not recommend using `/me-review:indicator-quality` more than once
