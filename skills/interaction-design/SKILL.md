---
name: interaction-design
description: Production-grade interaction design skill for user flows, micro-interactions, state management, and behavioral patterns
sasmp_version: "1.3.0"
bonded_agent: 03-interaction-design
bond_type: PRIMARY_BOND
version: "2.0.0"
---

# Interaction Design Skill

> **Production-Grade Interaction Capability** - Systematic interaction design following cognitive psychology principles and motion design standards.

## Skill Overview

| Attribute | Value |
|-----------|-------|
| **Bonded Agent** | `03-interaction-design` |
| **Category** | Behavior & Motion |
| **Complexity** | Advanced |
| **Prerequisites** | User goals, platform context |

## Core Capabilities

### 1. Flow Design
```yaml
capability: design_user_flow
parameters:
  flow_type:
    type: enum
    values: [task, onboarding, checkout, error_recovery]
    required: true
  complexity:
    type: enum
    values: [linear, branching, complex]
  max_steps:
    type: integer
    range: [1, 10]

validation:
  - no_dead_ends: required
  - escape_routes: required
  - progress_indication: recommended

output:
  format: flow_diagram
  includes:
    - steps
    - decision_points
    - error_paths
    - success_paths
```

### 2. Micro-interactions
```yaml
capability: design_microinteraction
parameters:
  trigger:
    type: enum
    values: [click, hover, focus, scroll, gesture, system]
  feedback_type:
    type: enum
    values: [visual, haptic, audio, combined]

specs:
  timing:
    instant: "0-100ms"
    fast: "100-200ms"
    normal: "200-300ms"
    slow: "300-500ms"

  easing:
    enter: "ease-out"
    exit: "ease-in"
    move: "ease-in-out"
```

### 3. State Management
```yaml
capability: define_states
parameters:
  component_type:
    type: string
    required: true

state_matrix:
  component:
    - default
    - hover
    - active
    - focus
    - disabled
    - loading
    - error
    - success

  page:
    - empty
    - loading
    - partial
    - complete
    - error

  system:
    - online
    - offline
    - syncing
```

### 4. Gesture Design
```yaml
capability: design_gestures
parameters:
  platform:
    type: enum
    values: [touch, mouse, keyboard, voice]
  gesture_type:
    type: enum
    values: [tap, swipe, pinch, rotate, long_press, drag]

validation:
  - accessibility_alternative: required
  - no_system_conflict: required
  - discoverability: recommended
```

## Input Validation

```yaml
required_inputs:
  - user_goal: "string, what user wants to accomplish"
  - context: "object with platform, input_method"

optional_inputs:
  - constraints: object
  - existing_patterns: array
  - accessibility_level: enum

validation_rules:
  timing:
    min: 50
    max: 500
    error: "Animation timing must be 50-500ms"

  touch_target:
    min: 44
    error: "Touch targets must be at least 44px"
```

## Error Handling

### Common Errors
```yaml
errors:
  FLOW_DEAD_END:
    code: "IX001"
    message: "User cannot progress from this state"
    recovery:
      - add_back_navigation
      - add_escape_route
    auto_fix: true

  UNCLEAR_FEEDBACK:
    code: "IX002"
    message: "State change not communicated"
    recovery:
      - add_visual_feedback
      - add_haptic_feedback
    fallback: add_status_message

  GESTURE_CONFLICT:
    code: "IX003"
    message: "Gesture overlaps with system gesture"
    recovery:
      - use_alternative_gesture
      - add_button_fallback
    auto_fix: false

  COGNITIVE_OVERLOAD:
    code: "IX004"
    message: "Too many choices/steps"
    recovery:
      - progressive_disclosure
      - chunk_information
      - reduce_options
```

### Retry Logic
```javascript
const interactionRetry = {
  feedback_timing: {
    maxAttempts: 3,
    adjustment: 50, // ms adjustment
    direction: 'auto'
  },
  gesture_recognition: {
    threshold_adjustment: 0.1,
    fallback: 'button_alternative'
  }
};
```

## Logging & Observability

```yaml
logging:
  level: INFO
  events:
    - interaction_triggered
    - state_changed
    - animation_complete
    - gesture_recognized

metrics:
  - interaction_latency_p95
  - animation_frame_rate
  - gesture_success_rate
  - error_recovery_rate

alerts:
  slow_feedback:
    threshold: ">100ms"
    action: optimize_animation
```

## Quality Checklist

- [ ] All states have transitions defined
- [ ] Error states have recovery paths
- [ ] Loading states handle timeouts
- [ ] Animations respect reduced-motion
- [ ] Keyboard navigation complete
- [ ] Focus order logical
- [ ] Touch targets >= 44px
- [ ] Feedback immediate (<100ms)
- [ ] Gestures have button alternatives

## Usage Examples

### Design Checkout Flow
```yaml
invoke: interaction-design
parameters:
  capability: design_user_flow
  flow_type: checkout
  complexity: branching
  max_steps: 5
  include_error_paths: true
```

### Create Button Interaction
```yaml
invoke: interaction-design
parameters:
  capability: design_microinteraction
  trigger: click
  feedback_type: combined
  states: [pressed, released]
  timing: fast
```

## Troubleshooting

| Issue | Symptom | Solution |
|-------|---------|----------|
| Feedback missed | Users don't notice | Increase contrast, add channel |
| Accidental triggers | Unintended actions | Add confirmation, increase spacing |
| Flow feels slow | Perceived lag | Add optimistic UI, skeletons |
| Dead ends | Users stuck | Add escape routes, back navigation |

---
**Version**: 2.0.0 | **Updated**: 2025-12-30 | **Agent**: `03-interaction-design`
