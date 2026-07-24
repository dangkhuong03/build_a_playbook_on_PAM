# 04_OUTPUT_TEMPLATE.md

# Performance Ad Variations for Seasonal Hospitality Campaigns
## Output Contract Specification

**Version:** 1.0  
**Document Type:** PAM Playbook Output Contract

---

# Purpose

This document defines the standard output contract for the Performance Ad Variations Playbook.

The objective is to ensure that every execution produces:

- predictable outputs
- reusable artifacts
- structured deliverables
- platform-ready creative packages
- consistent quality
- machine-readable results
- human-readable summaries

This document defines **what** must be returned, not **how** it is generated.

---

# Output Principles

Every execution must produce outputs that are:

- complete
- deterministic in structure
- reusable
- traceable
- platform-ready
- factually accurate
- consistent with @Brand Guidelines
- suitable for storage as reusable @Artifacts

---

# Output Package

The Playbook returns one **Creative Package**.

The package consists of the following sections.

---

# 1. Campaign Summary

## Purpose

Summarize the validated campaign context used during creative generation.

## Required Fields

- Campaign Name
- Campaign Objective
- Campaign Type
- Destination
- Audience
- Promotion Type
- Offer Summary
- Campaign Period
- Platform(s)
- Language

## Notes

This section must summarize only validated information.

No interpretation.

No recommendations.

---

# 2. Marketing Strategy

## Purpose

Capture the strategic reasoning used throughout creative generation.

## Required Fields

- Positioning
- Primary Marketing Angle
- Emotional Angle
- Primary Value Proposition
- Supporting Value Proposition
- Audience Motivation
- Message Hierarchy
- Offer Priority
- Destination Priority
- CTA Strategy

## Notes

This section documents strategic decisions rather than campaign facts.

---

# 3. Creative Brief

## Purpose

Define the communication direction for all generated assets.

## Required Fields

- Core Message
- Communication Objective
- Creative Direction
- Visual Direction Summary
- Tone
- Benefit Hierarchy
- Messaging Constraints
- Brand References

## References

- @Brand Guidelines
- @Brand Assets

---

# 4. Headline Variations

## Purpose

Provide multiple distinct headline candidates.

## Structure

Each headline should include:

- Identifier
- Headline
- Strategic Intent
- Target Platform(s)

## Requirements

Headlines should be sufficiently differentiated for testing.

---

# 5. Primary Copy Variations

## Purpose

Provide multiple advertising copy variants.

## Structure

Each variation includes:

- Identifier
- Primary Copy
- Communication Focus
- Audience Fit
- Platform Recommendation

---

# 6. CTA Variations

## Purpose

Provide ranked CTA recommendations.

## Structure

Each CTA includes:

- Identifier
- CTA
- Primary Objective
- Recommended Platform
- Reasoning

---

# 7. Visual Concepts

## Purpose

Describe visual direction for creative production.

This section defines concepts only.

It does not contain final artwork.

## Structure

Each concept includes:

- Identifier
- Hero Scene
- Composition
- Visual Hierarchy
- Focal Point
- Environment
- People
- Hospitality Cues
- Luxury Cues
- Color Guidance
- Asset References

## References

Consult:

- @Brand Assets
- @Brand Guidelines

---

# 8. Platform Variants

## Purpose

Describe platform-specific creative adaptations.

## Required Platforms

Include only requested platforms.

Possible platforms include:

- Facebook
- Instagram
- Google Display
- Google Responsive Display
- Landing Hero
- OTA Banner

## Structure

Each platform variant includes:

- Platform
- Headline Selection
- Copy Selection
- CTA Selection
- Layout Recommendation
- Adaptation Notes

---

# 9. Creative Rationale

## Purpose

Explain why the generated creative package aligns with campaign objectives.

## Required Fields

- Strategic Alignment
- Audience Alignment
- Platform Alignment
- Offer Alignment
- Positioning Alignment
- Creative Diversity Summary

This section explains reasoning rather than campaign facts.

---

# 10. QA Report

## Purpose

Summarize quality evaluation results.

## Required Fields

- Overall Status
- Overall Score
- Brand Consistency
- Offer Accuracy
- Destination Accuracy
- Grammar
- Readability
- Platform Compliance
- Audience Alignment
- Creative Diversity
- Critical Findings
- Recommended Actions

## References

Validation must consider:

- @Brand Guidelines
- Approved campaign data

---

# Markdown Output Template

```markdown
# Campaign Summary

## Campaign
- Name:
- Objective:
- Type:
- Destination:
- Audience:
- Promotion:
- Offer:
- Campaign Period:
- Platform(s):
- Language:

---

# Marketing Strategy

## Positioning

...

## Marketing Angle

...

## Emotional Angle

...

## Value Proposition

...

## Message Hierarchy

...

---

# Creative Brief

## Core Message

...

## Creative Direction

...

## Tone

...

## Visual Direction Summary

...

## Constraints

...

---

# Headline Variations

## H01

...

## H02

...

...

---

# Primary Copy Variations

## C01

...

## C02

...

---

# CTA Variations

## CTA01

...

## CTA02

...

---

# Visual Concepts

## Concept 01

### Hero Scene

...

### Composition

...

### Visual Hierarchy

...

### Asset References

@Brand Assets

---

## Concept 02

...

---

# Platform Variants

## Facebook

...

## Instagram

...

## Google Display

...

---

# Creative Rationale

## Strategic Alignment

...

## Audience Alignment

...

## Platform Alignment

...

---

# QA Report

## Overall Status

PASS / REVIEW / FAIL

## Scores

...

## Findings

...

## Recommended Actions

...
```

---

# JSON Output Template

```json
{
  "campaign_summary": {
    "campaign_name": "",
    "objective": "",
    "campaign_type": "",
    "destination": "",
    "audience": "",
    "promotion_type": "",
    "offer": "",
    "campaign_period": {},
    "platforms": [],
    "language": ""
  },
  "marketing_strategy": {
    "positioning": "",
    "marketing_angle": "",
    "emotional_angle": "",
    "value_proposition": "",
    "message_hierarchy": [],
    "cta_strategy": ""
  },
  "creative_brief": {
    "core_message": "",
    "creative_direction": "",
    "tone": "",
    "visual_direction_summary": "",
    "constraints": [],
    "brand_references": [
      "@Brand Guidelines",
      "@Brand Assets"
    ]
  },
  "headline_variations": [
    {
      "id": "H01",
      "headline": "",
      "strategic_intent": "",
      "platforms": []
    }
  ],
  "copy_variations": [
    {
      "id": "C01",
      "copy": "",
      "communication_focus": "",
      "audience_fit": "",
      "platforms": []
    }
  ],
  "cta_variations": [
    {
      "id": "CTA01",
      "cta": "",
      "objective": "",
      "platform": "",
      "reasoning": ""
    }
  ],
  "visual_concepts": [
    {
      "id": "VC01",
      "hero_scene": "",
      "composition": "",
      "visual_hierarchy": "",
      "focal_point": "",
      "environment": "",
      "people": "",
      "hospitality_cues": [],
      "luxury_cues": [],
      "color_guidance": "",
      "asset_reference": "@Brand Assets"
    }
  ],
  "platform_variants": [
    {
      "platform": "",
      "headline_id": "",
      "copy_id": "",
      "cta_id": "",
      "layout_notes": "",
      "adaptation_notes": ""
    }
  ],
  "creative_rationale": {
    "strategy_alignment": "",
    "audience_alignment": "",
    "platform_alignment": "",
    "offer_alignment": "",
    "positioning_alignment": "",
    "diversity_summary": ""
  },
  "qa_report": {
    "status": "",
    "overall_score": 0,
    "brand_consistency": 0,
    "offer_accuracy": 0,
    "destination_accuracy": 0,
    "grammar": 0,
    "readability": 0,
    "platform_compliance": 0,
    "audience_alignment": 0,
    "creative_diversity": 0,
    "critical_findings": [],
    "recommended_actions": []
  }
}
```

---

# Export Structure

The exported package should contain:

```text
Creative Package
│
├── Campaign Summary
├── Marketing Strategy
├── Creative Brief
├── Headlines
├── Copy
├── CTAs
├── Visual Concepts
├── Platform Variants
├── Creative Rationale
└── QA Report
```

All sections are mandatory unless explicitly disabled by workflow configuration.

---

# Naming Convention

Use deterministic, human-readable names.

## Creative Package

```text
<CampaignName>_<PlatformGroup>_<Language>_<Version>
```

---

## Headlines

```text
H01
H02
H03
...
```

---

## Copy

```text
C01
C02
C03
...
```

---

## CTA

```text
CTA01
CTA02
...
```

---

## Visual Concepts

```text
VC01
VC02
VC03
...
```

---

## Platform Variants

```text
FB
IG
GDN
OTA
LP
```

Platform identifiers should remain stable across exports.

---

# Folder Structure

Recommended export organization:

```text
Campaign/
│
├── Summary/
│
├── Strategy/
│
├── Headlines/
│
├── Copy/
│
├── CTA/
│
├── Visuals/
│
├── Platforms/
│
├── QA/
│
└── Metadata/
```

This structure is logical and may be mapped to the storage conventions supported by PAM.

---

# Artifact Structure

Approved outputs should be eligible for persistence as reusable `@Artifacts`.

Suggested artifact groupings:

```text
@Artifacts
│
├── Campaign Summaries
├── Marketing Strategies
├── Creative Briefs
├── Headline Libraries
├── Copy Libraries
├── CTA Libraries
├── Visual Concept Libraries
├── Platform Adaptations
└── QA Reports
```

Artifacts should include metadata such as:

- campaign identifier
- creation timestamp
- language
- destination
- audience
- platform
- version
- approval status

Only QA-approved outputs should be promoted to reusable artifacts.

---

# Success Indicators

An output package is considered complete when:

- all required sections are present
- campaign facts match validated inputs
- references to @Brand Guidelines and @Brand Assets are preserved where applicable
- all requested platform variants are included
- headline, copy, CTA, and visual concept sets are internally consistent
- the QA Report contains an overall status and actionable findings
- the package is structured for downstream human review and reusable artifact storage

Completion does not imply publication approval; final publication remains subject to the human review process defined elsewhere in the Playbook.