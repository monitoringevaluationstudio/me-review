---
description: Review a theory of change, causal pathway, or results chain for logical coherence, assumptions, evidence base, measurability, and scope
argument-hint: "[paste your theory of change or describe the causal logic]"
---

# /theory-of-change-review -- Theory of Change Review

Review a theory of change against M&E methodology standards. Produces a scored review across 7 dimensions with prioritized recommendations.

## Invocation

```
/me-review:theory-of-change-review

[paste your theory of change here]
```

## Workflow

### Step 1: Accept Input

Accept the ToC in any of these formats:
- **Full document:** Complete ToC narrative with or without diagram description
- **Diagram description:** User describes the visual diagram and pathways
- **Embedded in proposal:** ToC section extracted from a larger document
- **Results chain:** Linear pathway (activities to outputs to outcomes to impact)
- **Narrative description:** User describes the ToC verbally
- **Partial draft:** Incomplete ToC for early-stage feedback

If invoked with `$ARGUMENTS`, treat that as the ToC content to review.

If no ToC content is provided, prompt the user to supply one.

### Step 2: Classify the Document

Before scoring, identify the document type (Full ToC, Diagram only, Embedded in proposal, Results chain, Narrative description, or Partial Draft). State the classification explicitly at the top of the review and adjust expectations:
- **Diagram only:** Focus on logical coherence; flag missing narrative but don't FAIL completeness for it
- **Results chain:** Assess causal logic; note simplified scope
- **Partial Drafts:** Note gaps as "needs development" rather than FAIL for intentionally omitted sections

### Step 3: Handle Non-Standard Input

**Narrative description:** If the user describes the ToC rather than pasting it, first summarize your understanding of each pathway, then apply the review. Flag any elements the description did not address as "not confirmed present."

**Diagram description:** If only a visual is described, reconstruct the logic as a pathway table before reviewing.

### Step 4: Conduct 7-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **Logical Coherence** -- Does each level causally follow from the one below? Any logical leaps or circular logic?
2. **Assumptions Quality** -- Assumptions stated at each level? Testable? Risk-classified?
3. **Evidence Base** -- Causal links supported by evidence, research, or prior program results?
4. **Completeness** -- All 8 standard ToC elements present? Problem statement grounded?
5. **Measurability** -- Can each results level be measured? Indicators implied or explicit?
6. **Scope and Boundaries** -- Clear geographic, temporal, population boundaries? Contribution acknowledged?
7. **Pathways and Complexity** -- Multiple pathways for complex programs? Feedback loops? Unintended effects?

### Step 5: Calculate Overall Rating

- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

**Note:** A FAIL in Logical Coherence automatically triggers Major Issues regardless of other scores.

### Step 6: Generate Output

```
## Theory of Change Review Summary

**Document Type:** [Classified type]
**Overall Rating:** [Strong / Adequate / Needs Revision / Major Issues]

**Score Summary:**
| Section | Score |
|---------|-------|
| 1. Logical Coherence | PASS / PARTIAL / FAIL |
| 2. Assumptions Quality | PASS / PARTIAL / FAIL |
| 3. Evidence Base | PASS / PARTIAL / FAIL |
| 4. Completeness | PASS / PARTIAL / FAIL |
| 5. Measurability | PASS / PARTIAL / FAIL |
| 6. Scope and Boundaries | PASS / PARTIAL / FAIL |
| 7. Pathways and Complexity | PASS / PARTIAL / FAIL |

---

## Priority Recommendations

[3-5 highest-priority issues, ordered by severity. Lead with the specific finding, then the recommendation.]

1. **[Section Name]:** [Specific finding] -- [Specific recommendation]
2. ...

---

## Detailed Findings

### 1. Logical Coherence -- [PASS / PARTIAL / FAIL]
[Findings: assess each causal link, identify gaps or leaps]

### 2. Assumptions Quality -- [PASS / PARTIAL / FAIL]
[Findings: are assumptions stated, testable, risk-classified?]

### 3. Evidence Base -- [PASS / PARTIAL / FAIL]
[Findings: what evidence supports the causal logic?]

### 4. Completeness -- [PASS / PARTIAL / FAIL]
[Findings: which of the 8 standard elements are present/missing?]

### 5. Measurability -- [PASS / PARTIAL / FAIL]
[Findings: can results be measured? Are indicators implied?]

### 6. Scope and Boundaries -- [PASS / PARTIAL / FAIL]
[Findings: are geographic, temporal, population boundaries clear?]

### 7. Pathways and Complexity -- [PASS / PARTIAL / FAIL]
[Findings: appropriate complexity? Multiple pathways? Unintended effects?]

---

## Design Flaw Flags
[List any common design flaws detected, folded into the relevant sections above]
```

## Output Rules

- Lead each finding with the specific gap or issue, not a generic category label
- State the standard or good-practice principle a finding rests on, in plain language
- For PARTIAL scores, state exactly what is present and what is missing
- For narrative/incomplete inputs, distinguish between "not present" and "not confirmed present"
- When reviewing sector-specific ToCs, apply the methodology-specific flags from the skill
- Do not penalize humanitarian programs for short causal chains or limited impact claims
