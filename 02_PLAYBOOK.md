# 02_PLAYBOOK.md

# Performance Ad Variations for Seasonal Hospitality Campaigns
## Standard Operating Procedure (SOP)

**Version:** 1.0  
**Document Type:** PAM Playbook  
**Purpose:** Workflow Definition

---

# Overview

This Playbook defines the complete operational workflow for transforming a validated hospitality campaign brief into a structured package of performance advertising creatives.

The workflow is reusable across:

- campaigns
- destinations
- audiences
- seasons
- platforms
- languages

This document defines **process**, not AI identity, input contracts, or output formats.

---

# Workflow Overview

```text
Campaign Brief
        │
        ▼
Validation
        │
        ▼
Audience Analysis
        │
        ▼
Marketing Strategy
        │
        ▼
Creative Strategy
        │
        ▼
Headline Generation
        │
        ▼
Copy Generation
        │
        ▼
CTA Generation
        │
        ▼
Visual Direction
        │
        ▼
Platform Adaptation
        │
        ▼
Quality Assurance
        │
        ▼
Export
```

Every stage must successfully complete before the next stage begins.

Stages may trigger retries when validation fails.

---

# Stage 1 — Campaign Brief

## Purpose

Normalize campaign information into a structured internal representation that becomes the single source of truth for downstream processing.

---

## Inputs

- Campaign brief
- Project metadata
- User request

---

## Processing

- Parse campaign objective.
- Identify campaign scope.
- Extract campaign entities.
- Normalize terminology.
- Resolve ambiguities where possible.
- Associate campaign with project context.

---

## Decision Logic

Determine whether:

- campaign intent is clear
- advertising objective exists
- campaign can continue

---

## Validation

Verify:

- campaign objective exists
- campaign purpose is understandable
- campaign scope is internally consistent

---

## Outputs

Structured Campaign Object

---

## Failure Conditions

- campaign objective missing
- campaign cannot be interpreted
- conflicting campaign definitions

Action:

Stop and request clarification.

---

# Stage 2 — Validation

## Purpose

Verify that all required campaign information is accurate, complete, and internally consistent before creative reasoning begins.

---

## Inputs

- Structured Campaign Object
- Verified campaign information
- @Connectors (when required)

---

## Processing

- Validate campaign metadata.
- Verify offer information.
- Verify destination.
- Verify campaign timing.
- Detect conflicts.
- Resolve authoritative values.

---

## Decision Logic

Determine whether campaign information is:

- verified
- incomplete
- contradictory

---

## Validation

Cross-check against:

- approved campaign data
- @Connectors (only when necessary)
- project-approved information

---

## Outputs

Validated Campaign Object

---

## Failure Conditions

- unverifiable offer
- conflicting promotion
- missing mandatory campaign information
- invalid destination
- invalid campaign period

Action:

Stop processing.

---

# Stage 3 — Audience Analysis

## Purpose

Translate audience definitions into communication requirements.

The goal is understanding—not segmentation.

---

## Inputs

- Validated Campaign
- Audience information
- Previous @Artifacts (optional)

---

## Processing

Identify:

- motivations
- concerns
- decision drivers
- preferred communication style
- benefit priorities
- emotional expectations

---

## Decision Logic

Determine:

- dominant customer motivation
- primary communication objective
- messaging hierarchy

---

## Validation

Ensure audience interpretation:

- aligns with campaign
- contains no unsupported assumptions
- remains internally consistent

---

## Outputs

Audience Profile

---

## Failure Conditions

- audience undefined
- audience conflicts with campaign objective
- audience impossible to infer safely

Action:

Request clarification.

---

# Stage 4 — Marketing Strategy

## Purpose

Determine the strategic foundation for every creative.

This stage decides **what should be communicated**, not **how it is written**.

---

## Inputs

- Validated Campaign
- Audience Profile
- @Brand Guidelines

---

## Processing

Determine:

- positioning
- value proposition
- marketing angle
- emotional angle
- message hierarchy
- offer prominence
- destination prominence

---

## Decision Logic

Balance:

- campaign objective
- audience needs
- verified offer
- premium positioning

---

## Validation

Verify strategy:

- aligns with campaign objective
- respects @Brand Guidelines
- preserves premium positioning

---

## Outputs

Marketing Strategy

---

## Failure Conditions

- inconsistent positioning
- conflicting strategic priorities
- unsupported value proposition

Action:

Re-evaluate strategy.

---

# Stage 5 — Creative Strategy

## Purpose

Convert marketing strategy into creative direction.

Creative Strategy defines communication principles before copywriting begins.

---

## Inputs

- Marketing Strategy
- @Brand Guidelines
- @Brand Assets

---

## Processing

Determine:

- communication hierarchy
- creative emphasis
- visual priorities
- narrative direction
- benefit ordering
- creative differentiation strategy

---

## Decision Logic

Select one coherent creative direction.

Avoid mixing incompatible concepts.

---

## Validation

Ensure:

- visual direction aligns with messaging
- messaging aligns with positioning
- hierarchy supports campaign objective

---

## Outputs

Creative Strategy

---

## Failure Conditions

- conflicting creative priorities
- inconsistent communication hierarchy
- weak alignment with campaign

Action:

Rebuild creative strategy.

---

# Stage 6 — Headline Generation

## Purpose

Produce diverse headline variations aligned with strategy.

---

## Inputs

- Creative Strategy
- Marketing Strategy

---

## Processing

Generate headline candidates.

Prioritize:

- clarity
- relevance
- campaign objective
- audience alignment

---

## Decision Logic

Evaluate each headline against:

- campaign objective
- platform suitability
- strategic consistency

---

## Validation

Reject headlines that:

- contradict verified facts
- violate @Brand Guidelines
- weaken positioning
- repeat existing variants excessively

---

## Outputs

Headline Set

---

## Failure Conditions

- insufficient diversity
- factual inconsistency
- excessive repetition

Action:

Regenerate.

---

# Stage 7 — Copy Generation

## Purpose

Produce persuasive primary advertising copy supporting the approved strategy.

---

## Inputs

- Marketing Strategy
- Creative Strategy
- Headline Set

---

## Processing

Generate multiple copy variants.

Maintain:

- factual integrity
- premium tone
- readability
- strategic consistency

---

## Decision Logic

Ensure copy supports:

- value proposition
- campaign objective
- audience motivations

---

## Validation

Verify:

- no fabricated information
- offer preserved
- destination accurate
- messaging consistent

---

## Outputs

Primary Copy Set

---

## Failure Conditions

- unsupported claims
- inaccurate promotion
- weak alignment with strategy
- repetitive messaging

Action:

Revise copy.

---

# Stage 8 — CTA Generation

## Purpose

Recommend calls-to-action aligned with campaign objective and platform intent.

---

## Inputs

- Marketing Strategy
- Platform information

---

## Processing

Generate ranked CTA candidates.

---

## Decision Logic

Evaluate:

- conversion intent
- friction level
- audience readiness
- platform expectations

---

## Validation

Reject CTAs that:

- exaggerate urgency
- misrepresent campaign
- conflict with verified information

---

## Outputs

CTA Set

---

## Failure Conditions

- CTA inconsistent with objective
- misleading action
- platform mismatch

Action:

Generate alternatives.

---

# Stage 9 — Visual Direction

## Purpose

Produce structured creative direction for visual production.

This stage defines design intent rather than generating final artwork.

---

## Inputs

- Creative Strategy
- @Brand Assets
- @Brand Guidelines

---

## Processing

Specify:

- visual hierarchy
- focal point
- composition
- scene priorities
- hospitality cues
- luxury cues
- supporting elements

---

## Decision Logic

Prioritize communication effectiveness over visual complexity.

---

## Validation

Verify recommendations:

- align with @Brand Assets
- preserve premium identity
- support campaign strategy

---

## Outputs

Visual Direction Specification

---

## Failure Conditions

- unsupported imagery
- conflict with brand identity
- unclear hierarchy

Action:

Revise visual direction.

---

# Stage 10 — Platform Adaptation

## Purpose

Adapt approved creative content for each delivery platform.

Platform adaptation changes presentation—not meaning.

---

## Inputs

- Headlines
- Copy
- CTA
- Visual Direction
- Platform requirements

---

## Processing

Adjust:

- structure
- hierarchy
- content length
- formatting
- layout guidance

---

## Decision Logic

Maintain strategic consistency across all platforms.

---

## Validation

Verify:

- platform compatibility
- readability
- consistency
- formatting

---

## Outputs

Platform-Specific Creative Variants

---

## Failure Conditions

- platform policy conflict
- formatting failure
- inconsistent messaging

Action:

Reformat.

---

# Stage 11 — Quality Assurance

## Purpose

Evaluate the complete creative package before export.

QA is mandatory.

No creative package may bypass this stage.

---

## Inputs

- Complete creative package
- @Brand Guidelines
- @Brand Assets

---

## Processing

Evaluate:

- factual accuracy
- offer accuracy
- destination accuracy
- brand consistency
- positioning
- grammar
- readability
- platform suitability
- diversity
- completeness

Generate structured QA findings.

---

## Decision Logic

Determine one outcome:

- PASS
- REVIEW
- FAIL

---

## Validation

Critical validation includes:

- campaign consistency
- verified information preserved
- premium positioning maintained
- no fabricated content
- compliance with @Brand Guidelines

---

## Outputs

QA Report

---

## Failure Conditions

Any critical issue including:

- fabricated information
- incorrect offer
- incorrect destination
- contradiction of @Brand Guidelines
- critical platform violation

Action:

Return to the earliest affected workflow stage.

---

# Stage 12 — Export

## Purpose

Package approved outputs into standardized deliverables.

---

## Inputs

- QA-approved creative package

---

## Processing

Assemble:

- structured outputs
- metadata
- reusable artifacts
- platform groupings

Link reusable outputs into @Artifacts where supported by the execution environment.

---

## Decision Logic

Export only QA-approved content.

---

## Validation

Verify:

- package completeness
- naming consistency
- export integrity

---

## Outputs

Final Creative Package

---

## Failure Conditions

- QA not passed
- incomplete package
- export formatting failure

Action:

Block export until resolved.

---

# Workflow Control

## Retry Policy

The workflow supports localized retries.

A failed stage should restart from the earliest stage affected by the failure instead of restarting the entire workflow.

Example:

```text
Headline Failure
        │
        ▼
Headline Generation
        │
        ▼
Copy Generation
        │
        ▼
CTA Generation
        │
        ▼
QA
```

Do not restart Audience Analysis if the failure is limited to headline quality.

---

# Knowledge Flow

```text
Campaign Brief
        │
        ▼
@Brand Guidelines
        │
        ▼
Verified Campaign Information
        │
        ▼
@Brand Assets
        │
        ▼
Previous @Artifacts
        │
        ▼
@Connectors (only if required)
        │
        ▼
Creative Generation
        │
        ▼
Quality Assurance
        │
        ▼
Export
```

Higher-priority knowledge sources always override lower-priority sources.

---

# Stage Dependencies

| Stage | Depends On |
|--------|------------|
| Campaign Brief | None |
| Validation | Campaign Brief |
| Audience Analysis | Validation |
| Marketing Strategy | Audience Analysis |
| Creative Strategy | Marketing Strategy |
| Headline Generation | Creative Strategy |
| Copy Generation | Headline Generation, Creative Strategy |
| CTA Generation | Marketing Strategy |
| Visual Direction | Creative Strategy, @Brand Assets |
| Platform Adaptation | Headlines, Copy, CTA, Visual Direction |
| Quality Assurance | All previous stages |
| Export | QA (PASS only) |

---

# Workflow Completion Criteria

The Playbook execution is complete only when:

- all workflow stages have completed successfully
- no critical validation errors remain
- QA status is **PASS**
- all outputs are internally consistent
- all references to @Brand Guidelines, @Brand Assets, @Artifacts, and @Connectors have been resolved where applicable
- the creative package is ready for downstream human approval or publishing without structural rework