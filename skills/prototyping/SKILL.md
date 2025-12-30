---
name: prototyping
description: Production-grade prototyping skill for wireframes, interactive prototypes, user testing, and design iteration
sasmp_version: "1.3.0"
bonded_agent: 04-prototyping
bond_type: PRIMARY_BOND
version: "2.0.0"
---

# Prototyping Skill

> **Production-Grade Prototyping Capability** - Rapid prototype creation and testing for design validation before development investment.

## Skill Overview

| Attribute | Value |
|-----------|-------|
| **Bonded Agent** | `04-prototyping` |
| **Category** | Design Validation |
| **Complexity** | Intermediate |
| **Prerequisites** | Design concept, testing goals |

## Core Capabilities

### 1. Wireframing
```yaml
capability: create_wireframe
parameters:
  fidelity:
    type: enum
    values: [sketch, low, medium]
    default: low
  screen_count:
    type: integer
    range: [1, 20]
  responsive:
    type: boolean
    default: true

output:
  format: figma_file
  includes:
    - screen_layouts
    - annotations
    - user_flow_connections
```

### 2. Interactive Prototype
```yaml
capability: build_prototype
parameters:
  fidelity:
    type: enum
    values: [low, medium, high]
    required: true
  interaction_level:
    type: enum
    values: [clickable, animated, data_driven]
  platform:
    type: enum
    values: [web, mobile, desktop]

features:
  clickable:
    - hotspots
    - screen_transitions
    - basic_navigation
  animated:
    - micro_interactions
    - transitions
    - loading_states
  data_driven:
    - variables
    - conditionals
    - realistic_data
```

### 3. User Testing
```yaml
capability: run_prototype_test
parameters:
  test_type:
    type: enum
    values: [moderated, unmoderated, guerrilla, five_second]
  participant_count:
    type: integer
    minimum: 5
    default: 6
  task_count:
    type: integer
    range: [3, 7]

metrics:
  - task_success_rate
  - time_on_task
  - error_count
  - satisfaction_score

success_criteria:
  task_completion: ">80%"
  satisfaction: ">4/5"
```

### 4. Design Iteration
```yaml
capability: iterate_design
parameters:
  feedback_source:
    type: enum
    values: [user_testing, stakeholder, analytics]
  iteration_scope:
    type: enum
    values: [minor, moderate, major]

process:
  1. analyze_feedback
  2. prioritize_changes
  3. implement_updates
  4. document_changes
  5. retest_if_needed
```

## Input Validation

```yaml
required_inputs:
  - design_concept: "object with screens, flows"
  - testing_goal: "string, what to validate"

optional_inputs:
  - existing_prototype: url
  - design_system: object
  - platform: enum

validation_rules:
  screens:
    min: 1
    max: 50
    error: "Prototype should have 1-50 screens"

  hotspots:
    overlap_check: true
    size_minimum: 44
```

## Error Handling

### Common Errors
```yaml
errors:
  PROTOTYPE_TOO_COMPLEX:
    code: "PT001"
    message: "Prototype scope too large for testing"
    recovery:
      - split_into_flows
      - focus_on_critical_path
    fallback: reduce_scope

  LOW_TEST_COMPLETION:
    code: "PT002"
    message: "Participants not completing tasks"
    recovery:
      - simplify_tasks
      - add_hints
      - check_prototype_bugs
    threshold: "<60%"

  ASSET_LOADING_ISSUES:
    code: "PT003"
    message: "Images/fonts not loading"
    recovery:
      - optimize_assets
      - use_fallbacks
      - check_permissions

  INCONCLUSIVE_RESULTS:
    code: "PT004"
    message: "Test results not actionable"
    recovery:
      - increase_sample
      - revise_tasks
      - segment_analysis
```

### Retry Logic
```javascript
const prototypeRetry = {
  testing: {
    maxAttempts: 2,
    adjustments: ['task_wording', 'sample_size'],
    fallback: 'qualitative_feedback'
  },
  assets: {
    maxAttempts: 3,
    backoff: 'exponential', // 1s, 2s, 4s
    fallback: 'placeholder_assets'
  }
};
```

## Logging & Observability

```yaml
logging:
  level: INFO
  events:
    - prototype_created
    - test_started
    - task_completed
    - iteration_applied

metrics:
  - prototype_screens_count
  - test_completion_rate
  - iteration_cycle_time
  - design_to_dev_fidelity

alerts:
  low_completion:
    threshold: "<70%"
    action: review_prototype
```

## Quality Checklist

- [ ] All critical paths prototyped
- [ ] Interactions match design specs
- [ ] Responsive breakpoints covered
- [ ] Error states included
- [ ] Loading states shown
- [ ] Empty states designed
- [ ] Hotspots clearly defined
- [ ] No dead-end screens
- [ ] Test tasks documented

## Usage Examples

### Create High-Fidelity Prototype
```yaml
invoke: prototyping
parameters:
  capability: build_prototype
  fidelity: high
  interaction_level: animated
  platform: mobile
  screens:
    - onboarding_1
    - onboarding_2
    - home
    - detail
```

### Run Usability Test
```yaml
invoke: prototyping
parameters:
  capability: run_prototype_test
  test_type: moderated
  participant_count: 6
  tasks:
    - "Complete the signup flow"
    - "Find a specific item"
    - "Complete a purchase"
```

## Troubleshooting

| Issue | Symptom | Solution |
|-------|---------|----------|
| Testers lost | High abandonment | Add navigation, affordances |
| Slow loading | Long waits | Optimize assets |
| Inconclusive | Mixed results | Rewrite tasks, increase sample |
| Dead ends | Can't proceed | Check all screen connections |

---
**Version**: 2.0.0 | **Updated**: 2025-12-30 | **Agent**: `04-prototyping`
