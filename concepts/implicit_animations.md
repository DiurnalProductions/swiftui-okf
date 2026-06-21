---
id: swiftui.implicit_animations
type: concept
title: Implicit Animations
description: Automatically animate state-driven view changes when an animation is attached.
tags: [swiftui, animation]
prerequisites:
  - swiftui.views
  - swiftui.body_recomputation
related:
  - swiftui.explicit_animations
  - swiftui.transitions
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`.animation(_:value:)` animates changes to animatable properties when a specified value changes.

## Mental model

Implicit animation says: **when this state changes, interpolate visual properties**. SwiftUI diffs the tree and animates property changes.

## Example

```swift
Circle()
    .frame(width: isExpanded ? 200 : 50, height: isExpanded ? 200 : 50)
    .animation(.spring, value: isExpanded)
```

## Common mistakes

- Using deprecated `.animation(_:)` without value — animates everything unpredictably.
- Animating non-animatable changes (identity swaps).

## Related concepts

- [Explicit Animations](/concepts/explicit_animations.md)
