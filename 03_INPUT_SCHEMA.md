# 03_INPUT_SCHEMA.md

# Performance Ad Variations for Seasonal Hospitality Campaigns
## Input Schema Specification

**Version:** 1.0  
**Document Type:** PAM Playbook Input Contract

---

# Purpose

This document defines the complete input contract for the Performance Ad Variations Playbook.

It specifies:

- accepted fields
- validation requirements
- default behaviors
- error handling
- input priorities
- normalization rules

This document does **not** define workflow execution or output formatting.

---

# Input Principles

The Playbook accepts only structured, verifiable campaign information.

Inputs must satisfy the following principles:

- complete
- internally consistent
- factually verifiable
- campaign-specific
- compatible with @Brand Guidelines
- compatible with approved @Brand Assets where visual assets are referenced

The Playbook must never fabricate missing mandatory information.

---

# Input Categories

Inputs are grouped into the following categories:

1. Campaign
2. Audience
3. Promotion
4. Destination
5. Platform
6. Creative
7. Brand
8. Localization
9. References
10. System Metadata

---

# Campaign Inputs

---

## Campaign Name

### Type

String

### Description

Unique campaign identifier used throughout the workflow.

### Required

Yes

### Allowed Values

Free text

### Validation Rules

- non-empty
- unique within project context
- human-readable

### Default Behaviour

None

### Error Handling

Request user input.

### Example

```
Summer Escape 2027
```

---

## Campaign Objective

### Type

Enum

### Description

Primary business objective.

### Required

Yes

### Allowed Values

- Bookings
- Revenue
- Occupancy
- Package Sales
- Loyalty
- Awareness
- Lead Generation
- Other (explicitly defined)

### Validation Rules

Exactly one primary objective.

### Default Behaviour

None.

### Error Handling

Stop execution.

### Example

```
Bookings
```

---

## Campaign Period

### Type

Date Range

### Description

Campaign validity window.

### Required

Yes

### Validation Rules

- valid date format
- start before end

### Default Behaviour

None.

### Error Handling

Reject invalid dates.

### Example

```
2027-05-01 → 2027-06-30
```

---

# Audience Inputs

---

## Audience Segment

### Type

Enum

### Description

Primary customer segment.

### Required

Yes

### Allowed Values

Project-defined audience taxonomy.

Examples include:

- Families
- Couples
- Luxury Travelers
- Groups
- Business Travelers
- Wellness Travelers
- Golf Travelers
- Domestic Travelers
- International Travelers

### Validation Rules

Single primary audience.

### Default Behaviour

None.

### Error Handling

Request clarification.

---

## Secondary Audience

### Type

Array<String>

### Description

Optional supporting audience segments.

### Required

Optional

### Validation Rules

Cannot contradict primary audience.

### Default Behaviour

Empty list.

---

# Promotion Inputs

---

## Offer

### Type

Object

### Description

Verified campaign offer.

### Required

Yes

### Validation Rules

Must be verifiable.

Must not conflict with campaign.

### Default Behaviour

None.

### Error Handling

Stop generation.

### Example

```
Save 20%
Breakfast Included
```

---

## Booking Window

### Type

Date Range

### Required

Optional

### Validation Rules

Must be within campaign period if supplied.

### Default Behaviour

Not referenced.

---

## Promotion Type

### Type

Enum

### Allowed Values

- Discount
- Package
- Member Offer
- Added Value
- Seasonal Promotion
- Flash Sale
- Other

### Required

Yes

---

# Destination Inputs

---

## Destination

### Type

String

### Description

Campaign destination.

### Required

Yes

### Validation Rules

Must be verified.

### Default Behaviour

None.

### Error Handling

Stop generation.

---

## Property

### Type

String

### Description

Specific hotel, resort or property.

### Required

Optional

### Validation Rules

Must belong to destination.

---

# Platform Inputs

---

## Platform

### Type

Enum

### Required

Yes

### Allowed Values

- Facebook
- Instagram
- Google Display
- Responsive Display
- Discovery
- Landing Hero
- OTA Banner

### Validation Rules

Supported platform only.

---

## Placement

### Type

Enum

### Required

Optional

Platform-specific placement.

---

# Creative Inputs

---

## Creative Objective

### Type

Enum

### Required

Optional

Examples

- Acquisition
- Conversion
- Retargeting
- Awareness

---

## Emotional Theme

### Type

String

### Required

Optional

Must support campaign strategy.

---

## Creative Constraints

### Type

Array<String>

### Required

Optional

Examples

- character limits
- prohibited wording
- campaign restrictions

---

# Brand Inputs

---

## Brand Guidelines Reference

### Type

Reference

### Required

Recommended

### Validation Rules

Reference must resolve successfully.

### Default Behaviour

Use project default.

### Notes

Do not duplicate Brand Guidelines.

Always reference:

```
@Brand Guidelines
```

---

## Brand Assets Reference

### Type

Reference

### Required

Optional

### Validation Rules

Reference must exist.

### Notes

Used for:

- imagery
- typography
- colors
- logos

Reference:

```
@Brand Assets
```

---

# Localization Inputs

---

## Language

### Type

String

### Required

Yes

### Validation Rules

Supported language.

---

## Locale

### Type

String

### Required

Optional

Used for localization.

---

# Reference Inputs

---

## Previous Artifact

### Type

Reference

### Required

Optional

Reference:

```
@Artifacts
```

Purpose

Reuse approved campaign components.

---

## External Data

### Type

Reference

### Required

Optional

Reference:

```
@Connectors
```

Use only for verified information.

---

# System Metadata

---

## Request ID

### Type

String

### Required

Optional

---

## User Notes

### Type

Markdown

### Required

Optional

---

## Project Tags

### Type

Array<String>

### Required

Optional

---

# Validation Matrix

| Field | Required | Validation | Failure Action |
|--------|----------|------------|----------------|
| Campaign Name | Yes | Non-empty | Ask user |
| Campaign Objective | Yes | Supported value | Stop |
| Campaign Period | Yes | Valid range | Stop |
| Audience | Yes | Valid segment | Ask user |
| Offer | Yes | Verified | Stop |
| Promotion Type | Yes | Supported | Stop |
| Destination | Yes | Verified | Stop |
| Platform | Yes | Supported | Stop |
| Language | Yes | Supported | Ask user |
| Brand Guidelines | Recommended | Reference available | Use project default if configured; otherwise warn |
| Brand Assets | Optional | Reference available | Continue |
| Previous Artifact | Optional | Reference resolves | Continue |
| Connector Data | Optional | Verified | Continue |

---

# Input Decision Tree

```text
Campaign Name?
        │
   No ──┴──► Request
        │
       Yes
        │
Campaign Objective?
        │
   No ──┴──► Stop
        │
       Yes
        │
Audience?
        │
   No ──┴──► Request
        │
       Yes
        │
Offer Verified?
        │
   No ──┴──► Stop
        │
       Yes
        │
Destination Verified?
        │
   No ──┴──► Stop
        │
       Yes
        │
Platform Supported?
        │
   No ──┴──► Stop
        │
       Yes
        │
Language Available?
        │
   No ──┴──► Request
        │
       Yes
        │
Continue Workflow
```

---

# Input Priority

When multiple sources provide the same field, resolve conflicts in the following order:

| Priority | Source |
|----------|--------|
| 1 | User-supplied Campaign Brief |
| 2 | Verified Campaign Information |
| 3 | @Brand Guidelines (for brand-related constraints only) |
| 4 | @Brand Assets (for visual references only) |
| 5 | Previous @Artifacts |
| 6 | @Connectors |
| 7 | System Defaults |

Lower-priority sources must never override higher-priority sources.

---

# JSON Example

```json
{
  "campaign": {
    "name": "Summer Escape 2027",
    "objective": "Bookings",
    "period": {
      "start": "2027-05-01",
      "end": "2027-06-30"
    }
  },
  "audience": {
    "primary": "Families",
    "secondary": []
  },
  "promotion": {
    "type": "Discount",
    "offer": {
      "title": "Save 20%",
      "verified": true
    },
    "booking_window": {
      "start": "2027-05-01",
      "end": "2027-06-15"
    }
  },
  "destination": {
    "name": "Phu Quoc",
    "property": "Example Resort"
  },
  "platform": {
    "channel": "Facebook",
    "placement": "Feed"
  },
  "creative": {
    "objective": "Conversion",
    "emotional_theme": "Relaxation",
    "constraints": []
  },
  "brand": {
    "guidelines": "@Brand Guidelines",
    "assets": "@Brand Assets"
  },
  "references": {
    "artifacts": "@Artifacts",
    "connectors": "@Connectors"
  },
  "localization": {
    "language": "en",
    "locale": "en-US"
  },
  "metadata": {
    "request_id": "REQ-001",
    "tags": ["summer", "family"]
  }
}
```

---

# Markdown Example

```markdown
# Campaign

Name: Summer Escape 2027

Objective: Bookings

Campaign Period:
- Start: 2027-05-01
- End: 2027-06-30

# Audience

Primary:
- Families

Secondary:
- None

# Promotion

Type:
- Discount

Offer:
- Save 20%

Booking Window:
- 2027-05-01 → 2027-06-15

# Destination

Destination:
- Phu Quoc

Property:
- Example Resort

# Platform

Channel:
- Facebook

Placement:
- Feed

# Localization

Language:
- English

Locale:
- en-US

# References

Brand:
- @Brand Guidelines

Assets:
- @Brand Assets

Previous Work:
- @Artifacts

External Verification:
- @Connectors

# Notes

No additional constraints.
```

---

# Input Readiness Criteria

The Playbook may proceed only when:

- all mandatory fields are present
- mandatory values pass validation
- required references resolve or have an approved fallback
- no conflicting campaign information exists
- campaign facts are verified
- destination and offer are validated
- the requested platform is supported

If any mandatory requirement fails, creative generation must not begin.