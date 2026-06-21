---
id: swiftui.transitions
type: concept
title: Transitions
description: Animate view insertion and removal with asymmetric or combined transitions.
tags: [swiftui, animation]
prerequisites:
  - swiftui.explicit_animations
related:
  - swiftui.matched_geometry_effect
  - swiftui.identity
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`.transition()` defines how views appear and disappear when conditionally inserted. Combine with `withAnimation` for insert/remove animation.

## Mental model

Transitions affect **view lifecycle**, not property changes. `.opacity.combined(with: .scale)` is common for conditional content.

## Example

```swift
if showDetail {
    DetailView()
        .transition(.move(edge: .trailing).combined(with: .opacity))
}
```

## Common mistakes

- Expecting transitions without conditional insertion.
- Forgetting `withAnimation` when toggling visibility.

## Related concepts

- [Matched Geometry Effect](/concepts/matched_geometry_effect.md)
