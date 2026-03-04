---
description: Review an evaluation final report for structural completeness, finding quality, evidence anchoring, limitation awareness, recommendation specificity, and accessibility
argument-hint: "[paste your evaluation report or describe the findings]"
---

# /evaluation-report-review -- Evaluation Report Review

Review an evaluation final report against M&E quality standards. Produces a scored review across 6 sections with issue classification (Critical/Important/Minor) and priority action list.

## Invocation

```
/me-review:evaluation-report-review

[paste your evaluation report here]
```

## Workflow

### Step 1: Accept Input

Accept the report in any of these formats:
- **Full document:** Complete evaluation report text
- **Document extract:** Key sections (findings, recommendations, limitations)
- **Narrative description:** User describes findings and main conclusions
- **File reference:** User points to a report to review

If invoked with `$ARGUMENTS`, treat that as the report content to review.

If no report is provided, prompt the user to supply one. If the user describes an evaluation without a written report, help them identify what the report should contain.

### Step 2: Classify Document Type

Identify the document type before reviewing (see skill methodology for classification table). State the document type at the top of the review and calibrate expectations accordingly.

For findings briefs or rapid assessments, note that methodology may be brief intentionally — focus on actionability and evidence anchoring rather than penalizing for lighter methodology coverage.

For mid-term evaluations, note if findings are labeled "preliminary" or "emerging" — adjust expectations accordingly.

For data summaries, assess as source material, not findings narrative.

### Step 3: Conduct 6-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **Structural Completeness** — Executive summary, methodology, findings by question, evidence, limitations, conclusions, recommendations all present?
2. **Finding Quality** — Data-backed, logical, significant, actionable?
3. **Evidence Anchoring** — Sources cited? Sufficient detail? Triangulation present?
4. **Limitation Awareness** — Scope stated? Design limitations disclosed? Implications discussed?
5. **Recommendation Specificity** — Specific actions? Prioritized? Linked to findings?
6. **Tone & Accessibility** — Appropriate for audience? Balanced? Well-organized?

### Step 4: Classify Issues by Severity

For each finding, classify:
- **Critical (must address):** Findings unreliable, limitations hidden, recommendations misleading
- **Important (should address):** Reduces clarity or credibility; limits usefulness of findings
- **Minor (nice to address):** Best practice improvements; does not affect core quality

### Step 5: Calculate Overall Rating

Based on section scores:
- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

**Critical weighting:** A FAIL in Evidence Anchoring (Section 3) or Limitation Awareness (Section 4) automatically triggers **Major Issues** regardless of other scores.

### Step 6: Generate Output

Produce the structured review with summary table, strengths, classified issues with specific fixes, and detailed findings.

When recommending changes, provide specific language the user can insert, not just abstract advice. For structural gaps, suggest sections to add.

## Output Format

```
## Evaluation Report Review Summary

**Document:** [Title/reference]
**Document Type:** [Full Report / Findings Brief / Performance Report / Impact Assessment / Mid-term / Rapid Assessment]
**Evaluation Type:** [Process / Outcome / Impact / Performance / Formative / Other]
**Overall Rating:** [Strong / Adequate / Needs Revision / Major Issues]

### Section Scores

| Section | Rating | Key Finding |
|---------|--------|-------------|
| Structural Completeness | [PASS/PARTIAL/FAIL] | [one-line summary] |
| Finding Quality | [PASS/PARTIAL/FAIL] | [one-line summary] |
| Evidence Anchoring | [PASS/PARTIAL/FAIL] | [one-line summary] |
| Limitation Awareness | [PASS/PARTIAL/FAIL] | [one-line summary] |
| Recommendation Specificity | [PASS/PARTIAL/FAIL] | [one-line summary] |
| Tone & Accessibility | [PASS/PARTIAL/FAIL] | [one-line summary] |

### Strengths
- [What the report does well]

### Critical Issues (Must Address)
1. [Issue — why it matters — specific fix]

### Important Issues (Should Address)
1. [Issue — why it matters — specific fix]

### Minor Improvements
1. [Improvement — rationale]

### Detailed Findings
[Section-by-section analysis with specific references to report text]
```

## Notes

- A findings report is the record of what the evaluation discovered, not a marketing document. Honest findings — even negative ones — are more valuable than polished findings.
- Calibrate expectations to the document type. A rapid assessment brief is intentionally shorter than a full evaluation report.
- Consider context: a $20K evaluation of a small program has different reporting expectations than a $500K multi-country impact evaluation.
- If the report is generally strong, say so. Not every report needs major revision.
- **Recommendations should be actionable.** If recommendations read like policy papers or wishful thinking, flag that.
- **If the evaluation has limitations, they should be disclosed.** Hiding limitations — or putting them in the appendix in small print — breaks stakeholder trust.
- For program design review beyond the evaluation scope, use `/me-review:logframe-review`.
- For TOR review or commissioning brief feedback, use `/me-review:tor-review`.
