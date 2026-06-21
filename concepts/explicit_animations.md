---
id: swiftui.explicit_animations
type: concept
title: Explicit Animations
description: Wrap state changes in withAnimation to drive coordinated animated updates.
tags: [swiftui, animation]
prerequisites:
  - swiftui.implicit_animations
related:
  - swiftui.transitions
  - swiftui.matched_geometry_effect
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`withAnimation { }` wraps state mutations, causing dependent view changes to animate together.

## Mental model

Explicit animation is **intent**: you decide exactly when animation starts, often tied to user actions.

## Example

```swift
Button("Toggle") {
    withAnimation(.easeInOut) { isExpanded.toggle() }
}
```

## Common mistakes

- Mixing conflicting implicit and explicit animations.
- Animating inside `body` instead of action handlers.

## Related concepts

- [Transitions](/concepts/transitions.md)
