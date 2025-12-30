---
name: user-research
description: Production-grade user research skill for conducting interviews, creating personas, mapping journeys, and running usability tests
sasmp_version: "1.3.0"
bonded_agent: 01-ux-research
bond_type: PRIMARY_BOND
version: "2.0.0"
---

# User Research Skill

> **Production-Grade Research Capability** - Systematic user research methodologies for evidence-based design decisions.

## Skill Overview

| Attribute | Value |
|-----------|-------|
| **Bonded Agent** | `01-ux-research` |
| **Category** | Discovery & Research |
| **Complexity** | Intermediate |
| **Prerequisites** | Research goals, target user definition |

## Core Capabilities

### 1. User Interviews
```yaml
capability: conduct_interviews
parameters:
  interview_type:
    type: enum
    values: [exploratory, contextual, validation]
    required: true
  participant_count:
    type: integer
    minimum: 5
    default: 8
  duration_minutes:
    type: integer
    range: [30, 90]
    default: 45

validation:
  - participant_count >= 5: "NNGroup minimum for patterns"
  - recording_consent: required
  - note_taker_available: recommended

retry_logic:
  no_show:
    max_attempts: 3
    backoff: [1_day, 2_days, 3_days]
    fallback: recruit_replacement
```

### 2. Persona Creation
```yaml
capability: create_personas
parameters:
  persona_type:
    type: enum
    values: [proto, validated, quantitative]
  research_basis:
    type: string
    description: "Source data for persona"

output:
  format: persona_template
  sections:
    - demographics
    - goals_motivations
    - pain_points
    - behaviors
    - quotes
    - scenarios
```

### 3. Journey Mapping
```yaml
capability: map_journey
parameters:
  journey_scope:
    type: enum
    values: [current_state, future_state, service_blueprint]
  touchpoints:
    type: array
    min_items: 3

output:
  stages: array
  emotions: curve
  pain_points: highlighted
  opportunities: annotated
```

### 4. Usability Testing
```yaml
capability: usability_test
parameters:
  test_type:
    type: enum
    values: [moderated, unmoderated, guerrilla]
  task_count:
    type: integer
    range: [3, 7]
  participant_count:
    type: integer
    minimum: 5

metrics:
  - task_success_rate
  - time_on_task
  - error_count
  - satisfaction_rating
```

## Input Validation

```yaml
required_inputs:
  - research_goal: "string, min 10 chars"
  - target_users: "array, min 1 segment"

optional_inputs:
  - constraints: object
  - existing_data: array
  - stakeholder_questions: array

validation_rules:
  research_goal:
    pattern: "^(Understand|Discover|Validate|Explore|Identify).*"
    error: "Research goal should start with action verb"

  target_users:
    min_items: 1
    max_items: 5
    error: "Define 1-5 user segments"
```

## Error Handling

### Common Errors
```yaml
errors:
  INSUFFICIENT_PARTICIPANTS:
    code: "UR001"
    message: "Not enough participants recruited"
    recovery:
      - extend_recruitment_period
      - expand_channels
      - adjust_criteria
    fallback: guerrilla_testing

  BIASED_SAMPLE:
    code: "UR002"
    message: "Sample not representative"
    recovery:
      - stratified_sampling
      - quota_adjustments
    fallback: acknowledge_limitations

  DATA_SATURATION_NOT_REACHED:
    code: "UR003"
    message: "New themes still emerging"
    recovery:
      - additional_sessions
      - extended_analysis
    fallback: preliminary_findings

  CONTRADICTORY_DATA:
    code: "UR004"
    message: "Conflicting insights"
    recovery:
      - segment_analysis
      - triangulation
      - follow_up_research
```

### Retry Logic
```javascript
const researchRetry = {
  recruitment: {
    maxAttempts: 3,
    backoff: 'exponential', // 1d, 2d, 4d
    onFailure: 'expand_criteria'
  },
  sessions: {
    maxAttempts: 2,
    backoff: 'linear', // 1d, 2d
    onFailure: 'reschedule'
  },
  analysis: {
    maxAttempts: 1,
    onFailure: 'peer_review'
  }
};
```

## Logging & Observability

```yaml
logging:
  level: INFO
  events:
    - session_started
    - session_completed
    - insight_generated
    - analysis_complete

metrics:
  - recruitment_rate
  - session_completion_rate
  - insight_count
  - time_to_insight

alerts:
  low_recruitment:
    threshold: "<50% target at midpoint"
    action: escalate_to_stakeholder
```

## Quality Checklist

- [ ] Research questions clearly defined
- [ ] Methodology appropriate for goals
- [ ] Sample size adequate (n >= 5)
- [ ] Consent obtained and documented
- [ ] Data properly anonymized
- [ ] Bias mitigation applied
- [ ] Findings triangulated
- [ ] Insights actionable

## Usage Examples

### Basic Interview Study
```yaml
invoke: user-research
parameters:
  capability: conduct_interviews
  interview_type: exploratory
  participant_count: 8
  duration_minutes: 45
  research_goal: "Understand how users manage their daily tasks"
```

### Usability Test
```yaml
invoke: user-research
parameters:
  capability: usability_test
  test_type: moderated
  task_count: 5
  participant_count: 6
  prototype_url: "https://figma.com/proto/..."
```

## Troubleshooting

| Issue | Symptom | Solution |
|-------|---------|----------|
| Low recruitment | <50% target | Expand channels, increase incentive |
| No-shows | 3+ consecutive | Over-recruit 50%, send reminders |
| Short answers | <2 min responses | Use probing questions |
| Leading responses | Agreement bias | Review script for neutrality |

---
**Version**: 2.0.0 | **Updated**: 2025-12-30 | **Agent**: `01-ux-research`
