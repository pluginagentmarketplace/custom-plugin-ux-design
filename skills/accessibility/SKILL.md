---
name: accessibility
description: Production-grade accessibility skill for WCAG compliance, assistive technology support, and inclusive design auditing
sasmp_version: "1.3.0"
bonded_agent: 05-accessibility
bond_type: PRIMARY_BOND
version: "2.0.0"
---

# Accessibility Skill

> **Production-Grade Accessibility Capability** - Systematic accessibility auditing and remediation following WCAG 2.2 guidelines.

## Skill Overview

| Attribute | Value |
|-----------|-------|
| **Bonded Agent** | `05-accessibility` |
| **Category** | Compliance & Inclusion |
| **Complexity** | Advanced |
| **Prerequisites** | Design/code to audit |

## Core Capabilities

### 1. Accessibility Audit
```yaml
capability: run_audit
parameters:
  audit_scope:
    type: enum
    values: [component, page, flow, full_site]
    required: true
  target_level:
    type: enum
    values: [A, AA, AAA]
    default: AA
  methods:
    type: array
    values: [automated, keyboard, screen_reader, color]

output:
  format: audit_report
  includes:
    - overall_score
    - issues_by_severity
    - remediation_plan
    - wcag_mapping
```

### 2. Contrast Check
```yaml
capability: check_contrast
parameters:
  foreground:
    type: color
    format: [hex, rgb, hsl]
  background:
    type: color
    format: [hex, rgb, hsl]
  text_size:
    type: enum
    values: [normal, large]

thresholds:
  AA_normal: 4.5
  AA_large: 3.0
  AAA_normal: 7.0
  AAA_large: 4.5
  non_text: 3.0
```

### 3. Screen Reader Testing
```yaml
capability: test_screen_reader
parameters:
  screen_reader:
    type: enum
    values: [NVDA, JAWS, VoiceOver, TalkBack]
  browser:
    type: enum
    values: [Chrome, Firefox, Safari, Edge]

checklist:
  - headings: "Logical h1>h2>h3 hierarchy"
  - landmarks: "main, nav, aside, footer defined"
  - forms: "Labels properly associated"
  - images: "Alt text meaningful"
  - dynamic: "Live regions announce changes"
```

### 4. Keyboard Testing
```yaml
capability: test_keyboard
parameters:
  scope:
    type: enum
    values: [component, page, flow]

checks:
  - tab_order: "Follows visual order"
  - focus_visible: "Always visible, 3:1 contrast"
  - focus_trap: "Can escape all components"
  - shortcuts: "No conflicts with AT"
  - interactive: "All elements operable"
```

## Input Validation

```yaml
required_inputs:
  - audit_scope: "what to audit"
  - target_level: "A|AA|AAA"

optional_inputs:
  - assistive_tech: array
  - existing_issues: array

validation_rules:
  contrast_ratio:
    min: 1.0
    max: 21.0

  focus_indicator:
    min_contrast: 3.0
    min_size: "2px"
```

## Error Handling

### Common Errors
```yaml
errors:
  CONTRAST_FAILURE:
    code: "A11Y001"
    message: "Color contrast below threshold"
    wcag: "1.4.3"
    severity: critical
    recovery:
      - adjust_colors
      - increase_text_size
    auto_fix: true

  MISSING_ALT_TEXT:
    code: "A11Y002"
    message: "Image missing alternative text"
    wcag: "1.1.1"
    severity: critical
    recovery:
      - add_descriptive_alt
      - mark_decorative
    auto_fix: false

  KEYBOARD_TRAP:
    code: "A11Y003"
    message: "User cannot escape component"
    wcag: "2.1.2"
    severity: critical
    recovery:
      - add_escape_handler
      - fix_focus_management

  MISSING_FOCUS_INDICATOR:
    code: "A11Y004"
    message: "Focus not visible"
    wcag: "2.4.7"
    severity: major
    recovery:
      - add_focus_styles
      - ensure_3:1_contrast
```

### Retry Logic
```javascript
const a11yRetry = {
  contrast_fix: {
    maxAttempts: 5,
    adjustment: 0.1, // Lightness delta
    strategy: 'binary_search'
  },
  automated_scan: {
    maxAttempts: 3,
    backoff: 'linear',
    fallback: 'manual_check'
  }
};
```

## Logging & Observability

```yaml
logging:
  level: INFO
  events:
    - audit_started
    - issue_found
    - issue_fixed
    - audit_complete

metrics:
  - wcag_violations_count
  - accessibility_score
  - remediation_rate
  - regression_count

alerts:
  critical_violation:
    threshold: ">0"
    action: block_deployment
```

## Quality Checklist

- [ ] Automated scans pass (0 critical)
- [ ] Keyboard navigation complete
- [ ] Screen reader testing done
- [ ] Color contrast meets AA (4.5:1)
- [ ] Focus indicators visible (3:1)
- [ ] Form labels properly associated
- [ ] Images have appropriate alt text
- [ ] Headings hierarchical (h1>h2>h3)
- [ ] Landmarks defined (main, nav)
- [ ] Reduced motion respected

## Usage Examples

### Run Full Audit
```yaml
invoke: accessibility
parameters:
  capability: run_audit
  audit_scope: full_site
  target_level: AA
  methods: [automated, keyboard, screen_reader]
  output_format: detailed_report
```

### Check Color Contrast
```yaml
invoke: accessibility
parameters:
  capability: check_contrast
  foreground: "#333333"
  background: "#FFFFFF"
  text_size: normal
  suggest_alternatives: true
```

## WCAG Quick Reference

```yaml
level_A:
  "1.1.1": "Alt text for images"
  "1.3.1": "Semantic HTML structure"
  "2.1.1": "Keyboard accessible"
  "4.1.2": "Name, Role, Value"

level_AA:
  "1.4.3": "Contrast 4.5:1 (text)"
  "1.4.11": "Contrast 3:1 (non-text)"
  "2.4.7": "Focus visible"

level_AAA:
  "1.4.6": "Contrast 7:1"
  "3.1.5": "Reading level"
```

## Troubleshooting

| Issue | Symptom | Solution |
|-------|---------|----------|
| Screen reader wrong | Order/content incorrect | Fix DOM order, ARIA |
| Focus disappears | Lost after interaction | Manage focus explicitly |
| Contrast fails | Brand color conflict | Adjust lightness, use larger text |
| Keyboard trap | Can't escape modal | Add Escape key handler |

---
**Version**: 2.0.0 | **Updated**: 2025-12-30 | **Agent**: `05-accessibility` | **Standard**: WCAG 2.2
