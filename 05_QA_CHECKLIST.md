# 05_QA_CHECKLIST.md

# Performance Ad Variations for Seasonal Hospitality Campaigns
## Enterprise AI Quality Assurance Framework

**Version:** 1.0  
**Document Type:** PAM Playbook Quality Assurance Standard

---

# Purpose

This document defines the enterprise quality assurance (QA) framework for the Performance Ad Variations Playbook.

It establishes:

- standardized evaluation criteria
- scoring methodology
- acceptance thresholds
- retry policies
- human review requirements
- quality reporting standards

The QA framework evaluates the **output package**, not the workflow implementation.

---

# QA Principles

Quality assurance must ensure that every generated creative package is:

- factually correct
- brand consistent
- strategically aligned
- platform appropriate
- internally consistent
- reusable
- suitable for human approval

Quality evaluation must always prioritize:

1. factual accuracy
2. brand integrity
3. campaign consistency
4. customer relevance
5. creative quality

Creativity must never override correctness.

---

# Evaluation Categories

## 1. Brand Consistency

### Objective

Verify alignment with:

- @Brand Guidelines
- approved positioning
- approved messaging
- approved tone
- approved terminology

### Evaluation Criteria

- tone consistency
- positioning consistency
- messaging consistency
- terminology compliance
- premium hospitality perception

### Pass Requirements

No material conflicts with @Brand Guidelines.

---

## 2. Offer Accuracy

### Objective

Ensure campaign offers exactly match verified campaign information.

### Evaluation Criteria

- promotion accuracy
- package accuracy
- inclusions
- exclusions
- booking period
- promotional wording

### Pass Requirements

100% factual accuracy.

No invented offers.

---

## 3. Destination Accuracy

### Objective

Verify all destination references.

### Evaluation Criteria

- destination names
- property names
- geographical references
- destination-specific experiences

### Pass Requirements

All destination information must be verified.

---

## 4. Grammar

### Objective

Evaluate language quality.

### Evaluation Criteria

- grammar
- punctuation
- spelling
- syntax

### Pass Requirements

Professional publication quality.

---

## 5. Readability

### Objective

Measure communication clarity.

### Evaluation Criteria

- clarity
- sentence flow
- simplicity
- information hierarchy

### Pass Requirements

Content should be immediately understandable by the intended audience.

---

## 6. Audience Alignment

### Objective

Determine whether messaging aligns with the intended audience.

### Evaluation Criteria

- benefit prioritization
- emotional relevance
- vocabulary
- communication style
- customer motivation

### Pass Requirements

Messaging supports the validated audience profile.

---

## 7. Platform Compliance

### Objective

Verify platform suitability.

### Evaluation Criteria

- structure
- formatting
- readability
- CTA placement
- platform conventions

### Pass Requirements

Creative is suitable for the requested platform.

---

## 8. CTA Effectiveness

### Objective

Evaluate the quality of calls-to-action.

### Evaluation Criteria

- clarity
- actionability
- objective alignment
- friction level
- consistency

### Pass Requirements

CTA supports the campaign objective without misleading the user.

---

## 9. Creative Diversity

### Objective

Measure meaningful variation across generated creatives.

### Evaluation Criteria

- messaging diversity
- emotional diversity
- structural diversity
- wording diversity
- strategic diversity

### Pass Requirements

Variations must differ in communication strategy rather than superficial wording alone.

---

## 10. Visual Consistency

### Objective

Evaluate alignment of visual recommendations.

### References

- @Brand Assets
- @Brand Guidelines

### Evaluation Criteria

- visual hierarchy
- composition
- luxury positioning
- hospitality cues
- asset references

### Pass Requirements

Visual concepts are consistent with approved brand resources.

---

## 11. Data Integrity

### Objective

Verify factual correctness throughout the creative package.

### Evaluation Criteria

- verified campaign information preserved
- no fabricated facts
- no unsupported claims
- internal consistency
- reference integrity

### Pass Requirements

Zero factual contradictions.

---

# Scoring Rubric

Each evaluation category receives a score from **0–5**.

| Score | Meaning |
|------:|---------|
| 5 | Excellent — fully meets enterprise standard |
| 4 | Good — minor improvements possible |
| 3 | Acceptable — usable with recommended revisions |
| 2 | Weak — significant revision required |
| 1 | Poor — major issues present |
| 0 | Critical failure |

---

# Category Weights

| Category | Weight |
|----------|-------:|
| Brand Consistency | 15% |
| Offer Accuracy | 15% |
| Destination Accuracy | 10% |
| Grammar | 5% |
| Readability | 10% |
| Audience Alignment | 10% |
| Platform Compliance | 10% |
| CTA Effectiveness | 5% |
| Creative Diversity | 10% |
| Visual Consistency | 5% |
| Data Integrity | 15% |

**Total:** 100%

---

# Overall Quality Score

```
Overall Score
=
Σ(Category Score × Weight)
```

Normalize to a score out of **100**.

---

# PASS / REVIEW / FAIL Criteria

## PASS

Requirements:

- Overall Score ≥ 90
- No critical failures
- No factual errors
- No brand violations
- No unresolved QA findings

Outcome:

Ready for human approval or downstream publishing workflow.

---

## REVIEW

Requirements:

- Overall Score 75–89
- No critical factual errors
- Minor quality issues present

Outcome:

Revise identified issues and rerun QA before export.

---

## FAIL

Requirements:

- Overall Score < 75
- Any critical failure
- Any factual contradiction
- Any brand violation

Outcome:

Reject package.

Return to the earliest affected workflow stage.

---

# Critical Failure Conditions

The following conditions automatically result in **FAIL**, regardless of score:

## Brand

- contradiction of @Brand Guidelines
- incorrect brand positioning
- unauthorized messaging

---

## Offer

- invented promotion
- incorrect pricing
- incorrect package
- incorrect booking period

---

## Destination

- incorrect destination
- incorrect property
- fabricated location information

---

## Data Integrity

- fabricated facts
- fabricated statistics
- fabricated customer claims
- fabricated awards
- fabricated reviews

---

## Compliance

- deceptive urgency
- unsupported guarantees
- misleading comparisons
- prohibited language

---

## Output Integrity

- missing mandatory output sections
- corrupted output structure
- inconsistent campaign information

---

# Automatic Retry Rules

The Playbook should retry automatically when issues are localized and deterministic.

| Failure Type | Retry Stage |
|--------------|-------------|
| Low headline diversity | Headline Generation |
| Weak copy quality | Copy Generation |
| Weak CTA quality | CTA Generation |
| Platform formatting issue | Platform Adaptation |
| Visual inconsistency | Visual Direction |
| Readability issue | Copy Generation |
| Grammar issue | Copy Generation |

Retries should target only the earliest affected stage.

Do not restart the full workflow unless required.

Maximum automatic retries:

**3**

After the third unsuccessful retry, escalate to human review.

---

# Human Review Rules

Mandatory human review is required when:

- campaign facts cannot be verified
- multiple retry attempts fail
- business strategy is ambiguous
- conflicting campaign sources exist
- QA status remains REVIEW after maximum retries
- premium positioning is uncertain
- legal or compliance interpretation is required

Recommended reviewers may include:

- Brand Manager
- Marketing Manager
- Creative Lead
- Legal/Compliance Reviewer

---

# Escalation Matrix

| Issue | Escalation |
|------|------------|
| Brand inconsistency | Brand Manager |
| Offer conflict | Campaign Owner |
| Destination conflict | Campaign Owner |
| Legal wording | Compliance |
| Strategic ambiguity | Marketing Manager |
| Visual direction uncertainty | Creative Lead |

---

# Quality Gates

The creative package must pass each gate sequentially.

```text
Data Integrity
        │
        ▼
Brand Consistency
        │
        ▼
Campaign Consistency
        │
        ▼
Audience Alignment
        │
        ▼
Creative Quality
        │
        ▼
Platform Compliance
        │
        ▼
Export Readiness
```

A failed gate blocks all downstream gates.

---

# Quality Report Template

```markdown
# QA Report

## Overall Status

PASS | REVIEW | FAIL

---

## Overall Score

Score:
/100

---

## Category Scores

| Category | Score | Status |
|----------|------:|--------|
| Brand Consistency | | |
| Offer Accuracy | | |
| Destination Accuracy | | |
| Grammar | | |
| Readability | | |
| Audience Alignment | | |
| Platform Compliance | | |
| CTA Effectiveness | | |
| Creative Diversity | | |
| Visual Consistency | | |
| Data Integrity | | |

---

## Critical Findings

- ...

---

## Warnings

- ...

---

## Recommended Actions

- ...

---

## Retry Required

Yes / No

If Yes:

Restart From:

- Validation
- Audience Analysis
- Marketing Strategy
- Creative Strategy
- Headline Generation
- Copy Generation
- CTA Generation
- Visual Direction
- Platform Adaptation

---

## Human Review Required

Yes / No

Reviewer:

- Brand
- Marketing
- Creative
- Legal
- Other

---

## References Used

- @Brand Guidelines
- @Brand Assets
- @Artifacts
- @Connectors (if applicable)

---

## Final Decision

APPROVED

or

REVISION REQUIRED

or

REJECTED
```

---

# Enterprise Acceptance Criteria

The creative package is considered enterprise-ready only when all of the following are true:

- Overall QA status is **PASS**.
- Overall score meets or exceeds the PASS threshold.
- No critical failure conditions are present.
- All mandatory sections defined in the Output Contract are complete.
- Campaign facts exactly match validated campaign information.
- Recommendations are consistent with @Brand Guidelines.
- Visual guidance references approved @Brand Assets where appropriate.
- Outputs are structurally valid for export and eligible for persistence as reusable @Artifacts.
- No unresolved warnings remain that could materially affect publication quality.

Only packages meeting these criteria should progress to final human approval or publishing workflows.