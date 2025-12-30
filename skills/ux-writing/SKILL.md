---
name: ux-writing
description: Production-grade UX writing skill for microcopy, voice & tone, error messages, CTAs, and content design
sasmp_version: "1.3.0"
bonded_agent: 07-ux-writing
bond_type: PRIMARY_BOND
version: "2.0.0"
---

# UX Writing Skill

> **Production-Grade Content Capability** - Clear, concise, and human-centered interface copy that guides users and builds trust.

## Skill Overview

| Attribute | Value |
|-----------|-------|
| **Bonded Agent** | `07-ux-writing` |
| **Category** | Content Design |
| **Complexity** | Intermediate |
| **Prerequisites** | User context, UI constraints |

## Core Capabilities

### 1. Microcopy Creation
```yaml
capability: write_microcopy
parameters:
  content_type:
    type: enum
    values: [button, label, placeholder, tooltip, helper_text]
    required: true
  character_limit:
    type: integer
    range: [10, 150]
  tone:
    type: enum
    values: [neutral, friendly, urgent, celebratory]

limits:
  button: 25
  link: 50
  tooltip: 150
  helper_text: 100
```

### 2. Error Messages
```yaml
capability: write_error_message
parameters:
  error_type:
    type: enum
    values: [validation, system, permission, timeout, not_found]
  severity:
    type: enum
    values: [critical, warning, info]

structure:
  1. what_happened: "Brief explanation"
  2. why: "If helpful"
  3. what_to_do: "Clear next step"

tone_by_severity:
  critical: "Calm, clear, solution-focused"
  warning: "Helpful, proactive"
  info: "Friendly, instructive"
```

### 3. Empty States
```yaml
capability: write_empty_state
parameters:
  context:
    type: enum
    values: [new_user, no_results, completed, error]

structure:
  - headline: "Clear statement"
  - explanation: "Why empty (optional)"
  - action: "What to do next (CTA)"

examples:
  new_user:
    headline: "No projects yet"
    explanation: "Create your first project to get started."
    cta: "Create project"
```

### 4. Voice & Tone Guidelines
```yaml
capability: define_voice
parameters:
  brand_attributes:
    type: array
    min_items: 3
  tone_contexts:
    type: array
    values: [success, error, warning, neutral, onboarding]

output:
  - voice_principles
  - tone_matrix
  - word_list: [preferred, avoid]
  - examples_by_context
```

## Input Validation

```yaml
required_inputs:
  - content_type: "what to write"
  - user_context: "user goal, emotion, expertise"
  - action: "what user should understand/do"

optional_inputs:
  - character_limit: integer
  - brand_voice: object
  - localization_targets: array

validation_rules:
  button_text:
    starts_with: verb
    max_length: 25
    avoid: ["Submit", "Click here", "Yes", "OK"]

  error_message:
    includes_next_step: required
    no_blame_language: required
    max_length: 150
```

## Error Handling

### Common Errors
```yaml
errors:
  COPY_TOO_LONG:
    code: "UXW001"
    message: "Copy exceeds character limit"
    recovery:
      - progressively_shorten
      - prioritize_action_context
    auto_fix: true

  UNCLEAR_MEANING:
    code: "UXW002"
    message: "Copy meaning ambiguous"
    recovery:
      - A/B_test_alternatives
      - user_test_copy
    fallback: simplify_language

  TONE_MISMATCH:
    code: "UXW003"
    message: "Tone inappropriate for context"
    recovery:
      - adjust_for_context
      - reference_voice_guide
    auto_fix: true

  JARGON_DETECTED:
    code: "UXW004"
    message: "Technical terms used"
    recovery:
      - replace_with_plain_language
      - add_definition_if_necessary
```

### Retry Logic
```javascript
const copyRetry = {
  shortening: {
    maxAttempts: 3,
    priorities: ['action', 'context', 'details'],
    fallback: 'minimal_version'
  },
  clarity: {
    maxAttempts: 2,
    strategy: 'simplify_language',
    fallback: 'user_testing'
  }
};
```

## Logging & Observability

```yaml
logging:
  level: INFO
  events:
    - copy_created
    - copy_tested
    - copy_updated
    - voice_applied

metrics:
  - reading_ease_score
  - avg_sentence_length
  - cta_click_rate
  - error_recovery_rate

alerts:
  low_cta_performance:
    threshold: "<5% click rate"
    action: A/B_test_alternatives
```

## Quality Checklist

- [ ] Action-oriented (starts with verb)
- [ ] Active voice used
- [ ] Under character limit
- [ ] Free of jargon
- [ ] Consistent with brand voice
- [ ] Context-appropriate tone
- [ ] Localization-friendly
- [ ] Screen reader compatible
- [ ] Error messages have next steps
- [ ] Success messages confirm action

## Usage Examples

### Write Button Label
```yaml
invoke: ux-writing
parameters:
  capability: write_microcopy
  content_type: button
  action: "save user's changes"
  character_limit: 20
  tone: neutral
```

### Write Error Message
```yaml
invoke: ux-writing
parameters:
  capability: write_error_message
  error_type: validation
  context: "email field"
  severity: warning
  include_example: true
```

## Copy Patterns

```yaml
buttons:
  good: ["Save", "Save changes", "Create project"]
  avoid: ["Submit", "Yes", "Click here", "OK"]

errors:
  before: "Invalid email address entered"
  after: "Check your email format (example: name@company.com)"

confirmation:
  before: "Are you sure?" [Yes/No]
  after: "Delete project?" [Delete project/Keep project]
```

## Troubleshooting

| Issue | Symptom | Solution |
|-------|---------|----------|
| Too long | Truncates/wraps | Progressive shortening |
| Misunderstood | Wrong actions | A/B test alternatives |
| Frustrating | Support tickets | Remove blame, add solution |
| Inconsistent | Brand confusion | Reference voice guide |

---
**Version**: 2.0.0 | **Updated**: 2025-12-30 | **Agent**: `07-ux-writing`
