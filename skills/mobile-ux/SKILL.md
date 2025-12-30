---
name: mobile-ux
description: Production-grade mobile UX skill for iOS/Android patterns, touch gestures, responsive design, and platform-native experiences
sasmp_version: "1.3.0"
bonded_agent: 06-mobile-ux
bond_type: PRIMARY_BOND
version: "2.0.0"
---

# Mobile UX Skill

> **Production-Grade Mobile Capability** - Platform-specific mobile design following iOS HIG and Material Design 3 guidelines.

## Skill Overview

| Attribute | Value |
|-----------|-------|
| **Bonded Agent** | `06-mobile-ux` |
| **Category** | Platform Design |
| **Complexity** | Advanced |
| **Prerequisites** | Target platform, device context |

## Core Capabilities

### 1. Platform Design
```yaml
capability: design_for_platform
parameters:
  platform:
    type: enum
    values: [ios, android, cross_platform]
    required: true
  device_class:
    type: enum
    values: [phone, tablet, foldable]
  usage_context:
    type: enum
    values: [one_handed, two_handed, tablet]

guidelines:
  ios:
    reference: "Human Interface Guidelines"
    nav: "Tab bar (bottom)"
    touch: "44x44pt minimum"
  android:
    reference: "Material Design 3"
    nav: "Navigation bar (bottom)"
    touch: "48x48dp minimum"
```

### 2. Gesture Design
```yaml
capability: design_gestures
parameters:
  gesture_type:
    type: enum
    values: [tap, swipe, pinch, rotate, long_press, drag]
  platform:
    type: enum
    values: [ios, android]

validation:
  - accessibility_alternative: required
  - no_system_conflict: required
  - touch_target_size: ">= platform_minimum"

system_reserved:
  ios:
    - top_edge: "Control Center"
    - bottom_edge: "Home indicator"
  android:
    - bottom_edge: "Gesture navigation"
    - top_edge: "Notification shade"
```

### 3. Responsive Layout
```yaml
capability: create_responsive_layout
parameters:
  breakpoints:
    compact: "0-599dp"
    medium: "600-839dp"
    expanded: "840dp+"
  adaptation_strategy:
    type: enum
    values: [reflow, reveal, transform]

output:
  includes:
    - layout_per_breakpoint
    - component_adaptations
    - navigation_changes
```

### 4. Offline Design
```yaml
capability: design_offline_experience
parameters:
  offline_strategy:
    type: enum
    values: [cache_first, network_first, stale_while_revalidate]
  sync_pattern:
    type: enum
    values: [background, manual, on_connect]

components:
  - offline_indicator
  - cached_content_display
  - action_queue
  - sync_status
```

## Input Validation

```yaml
required_inputs:
  - platform: "ios|android|cross_platform"
  - feature_type: "what to design"

optional_inputs:
  - device_capabilities: array
  - connectivity: enum
  - usage_context: enum

validation_rules:
  touch_targets:
    ios_min: 44
    android_min: 48
    unit: "pt/dp"

  safe_areas:
    respect: required
    platforms: [ios, android]
```

## Error Handling

### Common Errors
```yaml
errors:
  TOUCH_TARGET_TOO_SMALL:
    code: "MUX001"
    message: "Touch target below platform minimum"
    recovery:
      - increase_to_minimum
      - add_padding
    auto_fix: true

  GESTURE_SYSTEM_CONFLICT:
    code: "MUX002"
    message: "Gesture conflicts with system gesture"
    recovery:
      - use_alternative_gesture
      - move_from_edge
      - add_button_fallback

  THUMB_ZONE_VIOLATION:
    code: "MUX003"
    message: "Primary action outside easy reach"
    recovery:
      - move_to_bottom
      - use_FAB
      - add_reachability

  OFFLINE_NOT_HANDLED:
    code: "MUX004"
    message: "No offline fallback"
    recovery:
      - implement_caching
      - add_offline_indicator
      - queue_actions
```

### Retry Logic
```javascript
const mobileRetry = {
  network: {
    maxAttempts: 3,
    backoff: 'exponential', // 1s, 2s, 4s
    fallback: 'show_cached'
  },
  gesture_recognition: {
    threshold_adjustment: 0.1,
    fallback: 'button_tap'
  }
};
```

## Logging & Observability

```yaml
logging:
  level: INFO
  events:
    - screen_loaded
    - gesture_recognized
    - offline_detected
    - sync_completed

metrics:
  - app_launch_time
  - interaction_latency
  - gesture_success_rate
  - offline_usage_duration

alerts:
  slow_launch:
    threshold: ">3s cold"
    action: optimize_startup
```

## Quality Checklist

- [ ] Touch targets >= 44pt (iOS) / 48dp (Android)
- [ ] Primary actions in thumb zone
- [ ] Platform navigation patterns followed
- [ ] Gestures have button alternatives
- [ ] Offline state handled gracefully
- [ ] Loading states < 100ms perceived
- [ ] Safe areas respected
- [ ] Dynamic Type / font scaling works
- [ ] Haptic feedback appropriate

## Usage Examples

### Design iOS Feature
```yaml
invoke: mobile-ux
parameters:
  capability: design_for_platform
  platform: ios
  device_class: phone
  usage_context: one_handed
  feature: "task_list"
```

### Create Responsive Layout
```yaml
invoke: mobile-ux
parameters:
  capability: create_responsive_layout
  breakpoints: [compact, medium, expanded]
  adaptation_strategy: reveal
  primary_content: "list"
  secondary_content: "detail"
```

## Platform Quick Reference

```yaml
ios:
  touch_target: "44x44pt"
  margins: "16pt"
  nav_primary: "Tab bar"
  font: "SF Pro"
  haptics: [impact, notification, selection]

android:
  touch_target: "48x48dp"
  margins: "16dp"
  nav_primary: "Navigation bar"
  font: "Roboto"
  motion: [emphasized, standard]
```

## Troubleshooting

| Issue | Symptom | Solution |
|-------|---------|----------|
| Hard to reach | Top actions missed | Move to bottom/FAB |
| System conflict | Wrong action triggers | Avoid edge gestures |
| Foldable breaks | Content on fold | Fold-aware layouts |
| Offline fails | Errors shown | Implement cache-first |

---
**Version**: 2.0.0 | **Updated**: 2025-12-30 | **Agent**: `06-mobile-ux` | **Standards**: iOS HIG, Material 3
