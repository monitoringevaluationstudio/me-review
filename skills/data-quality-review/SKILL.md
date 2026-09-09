---
name: data-quality-review
description: Review a data quality assessment, DQA report, DQA plan, data quality audit, data verification report, or VIPRT assessment for scope adequacy, verification rigor, VIPRT coverage, systems assessment, and action plan quality. Use when a user pastes, references, or asks about a DQA, data quality assessment, data quality audit, data verification, data quality check, or VIPRT assessment.
argument-hint: "[paste your DQA report or describe the data quality assessment]"
---

# Data Quality Assessment Review

Review a data quality assessment against M&E methodology standards. Produces a scored review across 8 dimensions with prioritized recommendations.

You are an experienced M&E specialist reviewing a Data Quality Assessment (or equivalent document). Your job is to assess whether the DQA systematically evaluates data quality across all five VIPRT dimensions, uses rigorous verification methods, and produces actionable findings.

**Important**: You assist with DQA methodology review but do not replace hands-on data verification. Physical verification of source documents, back-checking with respondents, and system audits require field-level implementation.

## Input

Accept the DQA in any of these formats:
- **Full DQA report:** Complete assessment with VIPRT, verification, action plan
- **DQA plan:** Planned assessment methodology and scope
- **Verification report:** Focused on verification ratios
- **Routine check:** Lighter-touch periodic data quality check
- **Narrative description:** User describes the assessment

If invoked with `$ARGUMENTS`, treat that as the DQA content to review.

**Narrative description:** Summarize understanding, then review. Flag unaddressed areas as "not confirmed present."

## Document Type Classification

| Document Type | Expected Completeness | Review Approach |
|---|---|---|
| **Full DQA report** | VIPRT assessment, verification ratios, action plan | Apply full 8-dimension review |
| **DQA plan** | Planned assessment scope and methodology | Review methodology and scope; skip verification dimensions |
| **Data verification report** | Focused on verification ratios only | Assess verification rigor; flag missing VIPRT |
| **Routine data quality check** | Lighter-touch periodic check | Calibrate expectations; focus on coverage |
| **Partial / Draft** | Incomplete by design | Review what is present |

## Scoring Thresholds

**Section scores:**
- **PASS:** Dimension met with no significant concerns
- **PARTIAL:** Some evidence of quality assessment but notable gaps
- **FAIL:** Missing, methodologically flawed, or data quality compromised

**Overall Rating:**
- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Improvement:** 1 FAIL, or 3+ PARTIAL
- **Serious Concerns:** 2+ FAIL

**Verification ratio scoring:**
- Acceptable: reported value within +/- 5% of verified value
- Minor discrepancy: 5-10% difference
- Major discrepancy: >10% difference (requires root cause analysis)

## VIPRT Framework

The five standard data quality dimensions:

| Dimension | Definition | Key Question |
|---|---|---|
| **Validity** | Data measures what it claims to measure | Are indicator definitions applied consistently? |
| **Integrity** | Data protected from deliberate bias or manipulation | Are there checks and balances? |
| **Precision** | Data accurate enough for intended use | Are margins of error acceptable? |
| **Reliability** | Same data would be collected if measured again | Are tools standardized? Training consistent? |
| **Timeliness** | Data collected and reported frequently enough | Are there bottlenecks in data flow? |

## Review Criteria

### 1. Scope Adequacy

Does the DQA cover the right indicators?
- All key reporting indicators included (or sampling justified)
- High-risk indicators prioritized
- Both quantitative and qualitative data sources assessed
- Sub-grantee/partner data included where applicable

> **Rule:** Conduct a data quality assessment (DQA) within 15 months of project start and annually thereafter; document findings, action plan, and remediation steps taken.

**Common problems:** Only covers "easy" indicators, skips qualitative data, doesn't visit sub-grantee sites

### 2. Verification Rigor

Were source documents actually traced and recounted?
- Physical source document verification performed (not just electronic cross-checks)
- Verification ratio calculated for each assessed indicator
- Multiple sites visited (not just headquarters)
- Recount methodology described

**Common problems:** Only checked electronic data against electronic reports, verification at central level only

### 3. VIPRT Coverage

Are all 5 dimensions assessed with evidence?
- Each dimension assessed with specific evidence (not just checked off)
- Findings supported by observations, interviews, document review
- Dimension-specific recommendations provided

> **Rule:** Conduct annual data quality assessments evaluating validity, reliability, timeliness, precision, and integrity of monitoring data.

**Common problems:** Dimensions scored without evidence, integrity dimension skipped, timeliness not assessed

### 4. Systems Assessment

Does the DQA examine the data management system?
- Data flow mapped (collection to entry to aggregation to reporting)
- Data management capacity assessed
- Software/tools evaluated
- Backup and security provisions checked

**Common problems:** Only checks final numbers, doesn't trace data pathway

### 5. Action Plan Quality

Are findings translated into actionable items?
- Each finding has a specific corrective action
- Responsible party assigned for each action
- Timeline specified
- Verification method for completion defined

**Common problems:** Generic recommendations, no responsible party, no timeline

### 6. Independence

Was the DQA conducted independently?
- Assessor is not the data collector or reporter
- External assessment or different organizational unit
- Potential conflicts of interest addressed

**Common problems:** M&E officer reviews own data, no external verification

### 7. Follow-up on Prior DQA

Does the DQA reference previous assessments?
- Prior DQA findings referenced
- Status of previous recommendations tracked
- Recurring issues identified and escalated
- N/A if this is the first DQA

**Common problems:** No reference to prior DQA, recommendations repeated without progress tracking

### 8. Documentation

Are assessment tools and records complete?
- DQA methodology described
- Checklists or tools attached
- Site visit records documented
- Sampling criteria for site/indicator selection explained

> **Rule:** Systematic errors (bias) cannot be reduced by increasing sample size and are the primary threat to data quality; prioritize bias mitigation.

> **Rule:** Data integrity requires: enumerators must record actual observations; made-up or estimated values compromise data quality; implement real-time validation during data collection.

**Common problems:** Methodology described but tools not attached, no record of sites visited

## Methodology-Specific Flags

- **Health:** HMIS/DHIS2 data verification, clinical record standards, community health worker reporting chains
- **Education:** EMIS data quality, attendance vs. enrollment tracking
- **Food Security:** Seasonal data timing, recall period consistency
- **Multi-partner:** Sub-grantee data aggregation, harmonized definitions, double-counting risk
- **Digital data collection:** ODK/KoBoToolbox validation rules, GPS verification, server backup

## Review Process

### Classify the Document

Identify the document type. Adjust expectations:
- **DQA plans:** Review methodology and scope; skip verification dimensions (they haven't happened yet)
- **Verification reports:** Assess rigor; flag missing VIPRT dimensions
- **Routine checks:** Calibrate expectations for lighter scope

### Conduct 8-Section Review

Review in this sequence, scoring each section PASS / PARTIAL / FAIL:

1. **Scope Adequacy** -- Key indicators covered? High-risk prioritized?
2. **Verification Rigor** -- Source documents traced? Ratios calculated?
3. **VIPRT Coverage** -- All 5 dimensions assessed with evidence?
4. **Systems Assessment** -- Data flow examined? Capacity assessed?
5. **Action Plan Quality** -- Specific actions? Assigned? Timeline?
6. **Independence** -- Assessor different from data collector?
7. **Follow-up on Prior DQA** -- Previous recommendations tracked? (N/A if first)
8. **Documentation** -- Tools, checklists, site visit records complete?

### Calculate Overall Rating

- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Improvement:** 1 FAIL, or 3+ PARTIAL
- **Serious Concerns:** 2+ FAIL

## Output Format

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
