---
name: ui-design
description: Production-grade UI design skill for visual design, component systems, typography, color theory, and design tokens
sasmp_version: "1.3.0"
bonded_agent: 02-ui-design
bond_type: PRIMARY_BOND
version: "2.0.0"
---

# UI Design Skill

> **Production-Grade Design Capability** - Systematic visual design following modern design system principles and accessibility standards.

## Skill Overview

| Attribute | Value |
|-----------|-------|
| **Bonded Agent** | `02-ui-design` |
| **Category** | Visual Design |
| **Complexity** | Advanced |
| **Prerequisites** | Brand guidelines, platform target |

## Core Capabilities

### 1. Visual Design
```yaml
capability: create_visual_design
parameters:
  design_scope:
    type: enum
    values: [component, screen, flow, system]
    required: true
  platform:
    type: enum
    values: [web, mobile, desktop, cross-platform]
  accessibility_level:
    type: enum
    values: [A, AA, AAA]
    default: AA

validation:
  - contrast_ratio >= 4.5: "WCAG AA text"
  - contrast_ratio >= 3.0: "WCAG AA non-text"
  - touch_target >= 44: "Minimum touch size"
```

### 2. Component Design
```yaml
capability: design_component
parameters:
  component_type:
    type: string
    required: true
  states:
    type: array
    default: [default, hover, active, focus, disabled]
  variants:
    type: array
    default: [primary, secondary, tertiary]
  sizes:
    type: array
    default: [sm, md, lg]

output:
  format: figma_component
  includes:
    - base_component
    - variants
    - documentation
    - usage_guidelines
```

### 3. Design Tokens
```yaml
capability: generate_tokens
parameters:
  token_categories:
    type: array
    values: [colors, typography, spacing, shadows, borders]
  format:
    type: enum
    values: [json, yaml, css_variables, tailwind]

output:
  structure:
    primitive: "Raw values"
    semantic: "Purpose-based aliases"
    component: "Component-specific tokens"
```

### 4. Design System
```yaml
capability: build_design_system
parameters:
  scope:
    type: enum
    values: [foundation, components, patterns, full]
  documentation_level:
    type: enum
    values: [minimal, standard, comprehensive]

output:
  includes:
    - token_definitions
    - component_library
    - pattern_library
    - usage_guidelines
    - governance_model
```

## Input Validation

```yaml
required_inputs:
  - design_brief: "object with component_type, context"
  - target_platform: "enum: web|mobile|desktop"

optional_inputs:
  - brand_guidelines: object
  - existing_design_system: boolean
  - wcag_level: enum

validation_rules:
  colors:
    format: "hex|rgb|hsl|oklch"
    contrast_check: automatic

  typography:
    scale_ratio: [1.125, 1.25, 1.333, 1.5]
    line_height_range: [1.2, 1.8]

  spacing:
    base_unit: 8
    scale: "mathematical"
```

## Error Handling

### Common Errors
```yaml
errors:
  CONTRAST_FAILURE:
    code: "UI001"
    message: "Color contrast below WCAG threshold"
    recovery:
      - adjust_lightness
      - suggest_alternatives
    auto_fix: true

  TYPOGRAPHY_COLLISION:
    code: "UI002"
    message: "Text elements overlap"
    recovery:
      - increase_line_height
      - adjust_spacing
    auto_fix: true

  TOKEN_INCONSISTENCY:
    code: "UI003"
    message: "Value not in token system"
    recovery:
      - map_to_nearest_token
      - create_new_token
    fallback: document_exception

  COMPONENT_BLOAT:
    code: "UI004"
    message: "Too many component variants"
    recovery:
      - consolidate_variants
      - use_composition
```

### Retry Logic
```javascript
const designRetry = {
  contrast_adjustment: {
    maxAttempts: 5,
    increment: 0.05, // Lightness adjustment
    direction: 'auto' // Lighter or darker
  },
  token_mapping: {
    maxAttempts: 3,
    strategy: 'nearest_neighbor'
  }
};
```

## Logging & Observability

```yaml
logging:
  level: INFO
  events:
    - component_created
    - token_generated
    - accessibility_check
    - design_exported

metrics:
  - component_count
  - token_coverage
  - accessibility_score
  - design_debt_ratio

alerts:
  low_token_usage:
    threshold: "<90%"
    action: audit_custom_values
```

## Quality Checklist

- [ ] Follows 8pt grid system
- [ ] Typography scale mathematical (1.25 ratio)
- [ ] Color contrast meets WCAG AA (4.5:1)
- [ ] Focus indicators visible (3:1)
- [ ] Touch targets >= 44px
- [ ] Responsive at all breakpoints
- [ ] Dark mode considered
- [ ] Design tokens documented
- [ ] Component variants complete

## Usage Examples

### Create Button Component
```yaml
invoke: ui-design
parameters:
  capability: design_component
  component_type: button
  states: [default, hover, active, focus, disabled, loading]
  variants: [primary, secondary, ghost, danger]
  sizes: [sm, md, lg]
```

### Generate Design Tokens
```yaml
invoke: ui-design
parameters:
  capability: generate_tokens
  token_categories: [colors, typography, spacing]
  format: css_variables
  theme_support: [light, dark]
```

## Troubleshooting

| Issue | Symptom | Solution |
|-------|---------|----------|
| Contrast failure | Red warning | Adjust color lightness |
| Font rendering | Thin on Windows | Use 400+ weight |
| Layout overflow | Content clipping | Check responsive breakpoints |
| Inconsistent spacing | Visual rhythm off | Audit token usage |

---
**Version**: 2.0.0 | **Updated**: 2025-12-30 | **Agent**: `02-ui-design`
