---
name: sampling-plan-review
description: Review a sampling plan, sampling strategy, sample size calculation, sampling methodology, survey design, or sampling frame for method appropriateness, sample size justification, frame quality, selection procedure, disaggregation feasibility, and practical feasibility. Use when a user pastes, references, or asks about a sampling plan, sample size, sampling strategy, sampling frame, survey methodology, survey design, or sampling approach.
---

# Sampling Plan Review

You are an experienced M&E specialist reviewing a sampling plan (or equivalent methodology document). Your job is to assess whether the sampling approach is appropriate, properly justified, and practically feasible, with particular attention to sample size calculation and representativeness.

**Important**: You assist with sampling methodology review but do not replace statistical consultation. Complex sampling designs (multi-stage cluster, stratified with optimal allocation, adaptive designs) should be validated by a statistician. You verify that the right questions are asked and the documentation is complete.

## Document Type Classification

| Document Type | Expected Completeness | Review Approach |
|---|---|---|
| **Standalone sampling plan** | Full methodology document | Apply full 7-dimension review |
| **Embedded in evaluation methodology** | Sampling section within a larger document | Extract sampling content, assess as standalone |
| **Embedded in baseline/survey protocol** | Part of a larger survey document | Extract sampling content |
| **Brief/outline** | High-level approach without detail | Flag missing elements; assess what is present |
| **Qualitative sampling strategy** | Purposive/theoretical sampling for qualitative research | Different criteria: selection rationale, diversity, saturation |

## Scoring Thresholds

**Section scores:**
- **PASS:** Methodologically sound, well-documented, appropriate for the research question
- **PARTIAL:** Exists but has gaps in documentation or methodological concerns
- **FAIL:** Missing, methodologically flawed, or would produce unrepresentative results

**Overall Rating:**
- **Strong:** 0 FAIL, max 1 PARTIAL
- **Adequate:** 0 FAIL, 2+ PARTIAL
- **Needs Revision:** 1 FAIL, or 3+ PARTIAL
- **Major Issues:** 2+ FAIL

**Critical weighting:** A FAIL in Method Appropriateness or Sample Size Justification automatically triggers **Major Issues**.

## Sampling Methods Reference

| Method | When to Use | Key Requirements | Common Pitfalls |
|---|---|---|---|
| **Simple Random (SRS)** | Complete sampling frame, accessible population | Frame, random number generator | Impractical for dispersed populations |
| **Systematic** | Ordered list available | Random start, regular interval | Periodic patterns in list |
| **Stratified** | Need subgroup precision | Stratum definitions, allocation | Disproportionate allocation needs weighting |
| **Cluster** | No individual frame, geographic dispersion | Cluster list, DEFF, PPS | Requires larger sample; DEFF underestimation |
| **Multi-stage** | Large surveys, multiple levels | Sampling at each stage documented | Compounding design effects |
| **Purposive** | Qualitative research, expert selection | Criteria documented, rationale explicit | Cannot generalize; misused for quantitative |
| **Convenience** | Pilot testing only | Limitations stated | Misused for prevalence estimates |
| **LQAS** | Monitoring coverage at decentralized level | Lot definitions, pre-specified threshold | Data-dependent threshold selection |

## Sample Size Calculation Parameters

Every sample size calculation must document:

| Parameter | Definition | Standard Default |
|---|---|---|
| Confidence level | Probability true value in range | 95% (z=1.96) |
| Margin of error | Acceptable precision | +/-5% for surveys |
| Expected proportion | Expected prevalence | 50% (most conservative) |
| Design effect (DEFF) | Cluster sampling adjustment | 1.0 SRS, 1.5-2.5 cluster |
| Power | Detecting real effects | 80% minimum |
| Non-response adjustment | Buffer for refusals | 10-20% uplift |

**Minimum cell size rule:** If any subgroup has <30 observations, note limitations and avoid statistical claims for that subgroup.

## Review Criteria

### 1. Method Appropriateness

Does the sampling method match the research question?
- Method can answer the stated objective (prevalence estimation needs probability sampling)
- Alternatives considered and rationale for chosen method stated
- Method feasible within available resources

> **Rule:** Using convenience sampling instead of random sampling within clusters completely invalidates CLQAS statistical properties and error rate guarantees.

**Common problems:** Convenience sampling for prevalence, cluster design without DEFF, SRS claimed but no frame

### 2. Sample Size Justification

Is the calculation complete with all parameters documented?
- All parameters stated and justified (confidence, precision, proportion, DEFF, power)
- Calculation shown or formula referenced
- Non-response buffer included
- Finite population correction applied if sample >5% of population

> **Rule:** Sample size calculation must include: minimum detectable effect size, power (80%+ default), confidence (95%), design effect (cluster ICC if applicable); document all assumptions; if <30 per cell, note limitations.

**Common problems:** Sample size asserted without calculation, DEFF missing for clusters, no non-response buffer

### 3. Sampling Frame Quality

Is the frame defined, accessible, and current?
- Frame source identified
- Completeness assessed
- Currency verified (how old is the list?)
- Coverage checked (does it include the full target population?)

**Common problems:** No frame documented, outdated lists, incomplete geographic coverage

### 4. Selection Procedure

Are step-by-step instructions provided?
- Random selection method specified (tables, software, systematic)
- Procedure replicable by someone else
- Replacement procedure for inaccessible units
- For multi-stage designs, procedure described at each stage

**Common problems:** "Randomly select" with no procedure, PPS without probability calculation

### 5. Disaggregation Feasibility

Is the sample large enough for required subgroup analyses?
- Minimum cell sizes calculated for each required disaggregation
- Power analysis for subgroup comparisons (if planned)
- Oversampling justified for small subgroups

**Common problems:** Total sample adequate but subgroups too small, no power analysis for comparisons

### 6. Practical Feasibility

Can the sample be achieved within constraints?
- Timeline allows for stated sample size
- Budget supports the number of sites/interviews
- Access constraints acknowledged and mitigated
- Contingency for inaccessible areas

**Common problems:** 200 villages in 2 weeks, no replacement procedure, no contingency

### 7. Limitations Transparency

Are limitations stated honestly with mitigations?
- Known limitations documented
- Impact on representativeness assessed
- Mitigation strategies proposed
- Remaining risks acknowledged

> **Rule:** LQAS with "data-dependent" threshold selection (testing multiple thresholds mid-collection) violates assumptions and inflates false-positive risk; pre-specify your single threshold before field work begins.

> **Rule:** In LQAS when clusters contain more than the design-specified units per cluster, randomly exclude excess units to maintain statistical assumptions.

**Common problems:** No limitations section, limitations mentioned but dismissed

## Methodology-Specific Flags

- **Health:** WHO 30x7 cluster immunization survey methodology, PPS required
- **Food Security:** Seasonal timing critical; CARI/FCS methodology sampling requirements
- **Education:** School-based vs. household-based produces different results; account for absenteeism
- **Humanitarian:** Access constraints, mobile populations, rapidly changing denominators
- **Multi-country:** Harmonized DEFF assumptions, comparable frames across countries
