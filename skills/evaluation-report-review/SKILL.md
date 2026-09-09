---
name: evaluation-report-review
description: Review an evaluation final report for structural completeness, finding quality, evidence anchoring, limitation awareness, recommendation specificity, and accessibility. Use when a user pastes, references, or asks about an evaluation report, final report, endline report, impact assessment, performance review, mid-term evaluation, summative evaluation, or evaluation findings document.
argument-hint: "[paste your evaluation report or describe the findings]"
---

# Evaluation Report Review

Review an evaluation final report against M&E quality standards. Produces a scored review across 6 sections with issue classification (Critical/Important/Minor) and priority action list.

You are an experienced evaluation specialist reviewing an evaluation final report or findings document. Your job is to assess whether the report presents findings clearly, is grounded in solid evidence, acknowledges its own limitations, and provides actionable recommendations that stakeholders can use.

**Important**: You assist with evaluation report quality review but do not replace evaluation commissioning or interpretation expertise. Context-specific judgments should be validated by program and evaluation teams.

## Input

Accept the report in any of these formats:
- **Full document:** Complete evaluation report text
- **Document extract:** Key sections (findings, recommendations, limitations)
- **Narrative description:** User describes findings and main conclusions
- **File reference:** User points to a report to review

If invoked with `$ARGUMENTS`, treat that as the report content to review.

If no report is provided, prompt the user to supply one. If the user describes an evaluation without a written report, help them identify what the report should contain.

## Document Classification

Before reviewing, identify the document type. Different documents warrant different expectations:

| Document Type | Expected Completeness | Review Approach |
|---|---|---|
| **Full Final Report** | Executive summary, methodology, findings per question, limitations, conclusions, recommendations, appendices | Apply full review methodology |
| **Findings Brief** | Key findings + key recommendations (no detailed methodology) | Focus on finding quality, evidence, and recommendation clarity; note methodology section is intentionally brief |
| **Performance Report** | Annual or periodic findings against indicators (lighter methodology depth) | Apply full review; note that performance reports may not require deep limitations discussion |
| **Impact Assessment** | Findings on causal change, methodology for assessing attribution | Apply full review with emphasis on evidence anchoring for causal claims |
| **Mid-Term Evaluation Report** | Learning-focused, may include emerging findings | Note if document includes "early/preliminary findings" disclaimer; apply review but note incomplete data may be intentional |
| **Rapid Assessment** | Quick findings for immediate decision-making (methodology may be brief) | Assess whether brevity is disclosed upfront; focus on actionability of recommendations |
| **Narrative Summary** | User describes findings verbally | Treat as Findings Brief; focus on whether core evidence and limitations are articulated |
| **Data Summary or Annex** | Tables, charts, or raw data without narrative interpretation | Note that this is source material, not a findings report; assess organization and completeness of data but not narrative quality |

## Issue Severity Framework

- **Critical (must address):** Issues that render findings unreliable, hide major limitations, or provide misleading recommendations. Examples: findings presented as fact with no evidence, causality claimed without counterfactual design, major limitations hidden until appendix, recommendations contradict own findings.
- **Important (should address):** Issues that reduce clarity, credibility, or usefulness of findings. Examples: evidence sources listed but not synthesized, mixed results not reconciled, limitations noted but implications for findings not explored.
- **Minor (nice to address):** Best practice improvements that enhance accessibility or polish but don't affect core quality. Examples: no executive summary, recommendations could be more specific, findings could use subheadings.

## Scoring Thresholds

**Section scores:**
- **PASS:** Section is complete, evidence-backed, and clear
- **PARTIAL:** Section exists but has significant gaps or inconsistencies
- **FAIL:** Section is missing, fundamentally flawed, or would mislead readers

**Overall Rating (based on section scores):**
- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

**Critical weighting:** A FAIL in Evidence Anchoring (Section 3) or Limitation Awareness (Section 4) automatically triggers **Major Issues** regardless of other section scores. These are foundational. Unsupported findings or hidden limitations cannot be offset by strong recommendations.

## 6-Section Review Criteria

### 1. Structural Completeness

A quality evaluation report should include:
- **Executive Summary:** Purpose, key findings, main recommendations (1-2 pages)
- **Methodology section:** Evaluation questions, approach (quantitative/qualitative/mixed), data sources, sample/site selection, limitations of design
- **Findings presented by evaluation question:** Organized response to each question asked
- **Evidence section:** What data supports each finding (quotes, data points, corroboration across sources)
- **Limitations section:** Scope boundaries (time, geography, population), design limitations (no comparison group, limited sample), implementation challenges affecting data quality
- **Conclusions:** Summary of what findings mean, how they answer the evaluation questions
- **Recommendations:** Specific, actionable next steps linked to findings (not to hopes or external ideas)

**Checklist:**
- Executive summary present and summarizes actual report (not generic overview)
- Methodology sufficient to understand how findings were generated
- Findings organized clearly (by question, outcome, theme, or location as appropriate)
- Evidence cited for each finding (not just assertions)
- Limitations section addresses scope, design, and implementation
- Recommendations present and linked to findings
- Report internally coherent (conclusions match findings, recommendations address findings)

> **Rule:** Report findings and interpretations accurately, fairly, and in context. Do not distort findings for external stakeholders or donors.

### 2. Finding Quality

**Data support:**
- Each finding grounded in data (quantitative, qualitative, or mixed)
- Not inferred without support or presented as speculation
- Corroborating evidence from multiple sources where possible (triangulation)
- Exceptions and edge cases noted (e.g., "Most respondents reported X, except in Z location where...")

> **Rule:** Findings should be derived directly from data collection and analysis, not from external assumptions or donor priorities.

**Logical coherence:**
- Findings relate directly to the evaluation questions asked
- Causal claims (if present) supported by design that enables causal inference
- Correlations presented as correlations, not causation (unless counterfactual design present)
- Mixed or contradictory findings reconciled or discussed (not hidden)

**Significance and relevance:**
- Magnitude of findings stated (how many, what percentage, how much change)
- Findings address outcomes/changes, not just activities delivered
- Findings highlight both successes and shortcomings (not one-sided)
- Findings address stakeholder priorities (program is solving the right problem)

> **Rule:** Findings should answer the evaluation questions fully, addressing intended and unintended outcomes.

**Actionability:**
- Findings point toward action (what should change, what should be sustained)
- Not lost in academic language or jargon unfamiliar to audience
- Implications for decision-making are clear (not requiring readers to infer)

### 3. Evidence Anchoring

**Source citation:**
- Each finding traces to specific data source (e.g., "78% of surveys," "KII with 12 district officials," "documents from Q1 reports")
- Not vague ("stakeholders said" without specifying who, how many, in what context)
- When paraphrasing or synthesizing, source still attributable

> **Rule:** All information and data must be referenced according to their source and checked for accuracy.

**Sufficiency and detail:**
- Evidence provided is sufficient to support the claim (not a single quote for a broad finding)
- Quotes or examples given where appropriate (especially for qualitative findings)
- Sample size, response rate, or data collection scope mentioned (gives reader sense of evidence weight)
- Data quality issues disclosed (e.g., "self-reported, not verified," "incomplete data from 2 sites")

**Triangulation:**
- For major findings, evidence comes from multiple sources (surveys + KIIs, male + female respondents, different sites, different time periods)
- Where triangulation is not present, acknowledged as limitation
- If finding contradicts other data, this discrepancy addressed (not ignored)

> **Rule:** Use multiple data collection methods and cross-check findings across sources to increase credibility and reduce bias.

### 4. Limitation Awareness

**Scope transparency:**
- Geographic scope stated (which areas included/excluded)
- Population scope stated (which populations represented/not represented)
- Time scope stated (when data collected, what period findings apply to)
- Scope limitations made explicit (findings apply to X setting, may not generalize to Y)

**Design limitations:**
- Comparison/counterfactual approach disclosed (impact evaluation: was a comparison group used? If not, how are you accounting for what would have happened anyway?)
- Sample limitations noted (random vs. purposive, size, representativeness)
- Potential bias sources identified (selection bias, responder bias, enumerator effect, recall bias)
- Data quality issues disclosed (missing data, incomplete responses, data quality checks performed)

**Implementation limitations:**
- Challenges to data collection described (access issues, language barriers, security constraints, attrition)
- How these challenges affected findings (if substantially)
- Any deviations from evaluation plan noted and their implications

**Implications discussed:**
- Limitations section does not just list constraints. It explains what limitations mean for finding credibility
- Reader understands where to trust findings and where to treat with caution
- Limitations are not hidden in appendix. Their importance to interpretation is clear

> **Rule:** Identify and disclose limitations of the evaluation that affect findings validity, credibility, and utility. This builds trust; hiding limitations erodes it.

### 5. Recommendation Specificity

**Clarity and actionability:**
- Recommendations are specific actions, not aspirations (not "improve capacity" but "provide 3-day training in [skill] for [role] in [location]")
- Recommendations are feasible given findings and context (not wishful)
- Owner/responsible party implied or stated (Who will do this? When?)
- Success criteria or expected outcomes stated or implied

**Priority and sequencing:**
- Recommendations sequenced logically (what to do first, what depends on what)
- Recommendations prioritized by impact/feasibility (not all treated as equally urgent)
- Trade-offs noted where present (e.g., "This addresses indicator X but may delay outcome Y")

**Linkage to findings:**
- Each recommendation is traceable to a specific finding or set of findings
- Recommendation directly addresses the gap or opportunity identified
- Not adding ideas external to evaluation scope (program design questions belong in logframe-review, not here)

**Balance:**
- Recommendations address both operational improvements (how to do better) and strategic questions (whether to continue, pivot, scale)
- If program is underperforming, recommendations are candid about scale of change needed
- If program is succeeding, recommendations sustain successes and address emerging gaps

### 6. Tone & Accessibility

**Appropriate for audience:**
- Language complexity matches stakeholder literacy (not academic jargon for practitioners; not oversimplified for technical audience)
- Acronyms defined on first use
- Local/sector terminology explained (M&E concepts defined, not assumed)
- Length and structure suit how findings will be used (1-page brief for quick decisions, detailed report for commissioning)

**Balanced and fair:**
- Positive and negative findings both presented clearly (not hidden or minimized)
- Nuance preserved (not collapsed to "good/bad" summary)
- Findings attributed fairly (not claiming credit for others' work, not scapegoating)
- Tone professional but honest (not defensive or dismissive of criticism)

**Accessibility:**
- Key findings surfaced in executive summary (readers should not need to read 50 pages to understand results)
- Findings organized intuitively (by question, outcome, or geography as appropriate, not random order)
- Visual elements used where helpful (tables for comparison, charts for trends)
- Appendices provided for technical detail without cluttering main narrative

> **Rule:** Present findings in a clear, accessible manner that diverse stakeholders can understand and use.

## Review Process

### Classify Document Type

Identify the document type before reviewing (see skill methodology for classification table). State the document type at the top of the review and calibrate expectations accordingly.

For findings briefs or rapid assessments, note that methodology may be brief intentionally. Focus on actionability and evidence anchoring rather than penalizing for lighter methodology coverage.

For mid-term evaluations, note if findings are labeled "preliminary" or "emerging". Adjust expectations accordingly.

For data summaries, assess as source material, not findings narrative.

### Conduct 6-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **Structural Completeness**: Executive summary, methodology, findings by question, evidence, limitations, conclusions, recommendations all present?
2. **Finding Quality**: Data-backed, logical, significant, actionable?
3. **Evidence Anchoring**: Sources cited? Sufficient detail? Triangulation present?
4. **Limitation Awareness**: Scope stated? Design limitations disclosed? Implications discussed?
5. **Recommendation Specificity**: Specific actions? Prioritized? Linked to findings?
6. **Tone & Accessibility**: Appropriate for audience? Balanced? Well-organized?

### Classify Issues by Severity

For each finding, classify:
- **Critical (must address):** Findings unreliable, limitations hidden, recommendations misleading
- **Important (should address):** Reduces clarity or credibility; limits usefulness of findings
- **Minor (nice to address):** Best practice improvements; does not affect core quality

### Calculate Overall Rating

Based on section scores:
- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

**Critical weighting:** A FAIL in Evidence Anchoring (Section 3) or Limitation Awareness (Section 4) automatically triggers **Major Issues** regardless of other scores.

## Output Format

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
1. [Issue, why it matters, specific fix]

### Important Issues (Should Address)
1. [Issue, why it matters, specific fix]

### Minor Improvements
1. [Improvement: rationale]

### Detailed Findings
[Section-by-section analysis with specific references to report text]
```

## Notes

- A findings report is the record of what the evaluation discovered, not a marketing document. Honest findings, even negative ones, are more valuable than polished findings.
- Calibrate expectations to the document type. A rapid assessment brief is intentionally shorter than a full evaluation report.
- Consider context: a $20K evaluation of a small program has different reporting expectations than a $500K multi-country impact evaluation.
- If the report is generally strong, say so. Not every report needs major revision.
- **Recommendations should be actionable.** If recommendations read like policy papers or wishful thinking, flag that.
- **If the evaluation has limitations, they should be disclosed.** Hiding limitations, or putting them in the appendix in small print, breaks stakeholder trust.
- For program design review beyond the evaluation scope, use `/me-review:logframe-review`.
- For TOR review or commissioning brief feedback, use `/me-review:tor-review`.
