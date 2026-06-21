---
id: swiftui.composition
type: concept
title: Composition Over Inheritance
description: Build complex interfaces by combining small views rather than subclassing base views.
tags: [swiftui, composition, architecture]
prerequisites:
  - swiftui.views
related:
  - swiftui.containers
  - swiftui.reusable_views
  - swiftui.modifiers
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

SwiftUI has no view subclassing. Complex UI is built by **composing** smaller views inside `body` and applying modifiers.

## Mental model

Think **Lego bricks**, not inheritance trees. Each brick has clear inputs and emits events upward.

## Example

```swift
struct ProfileScreen: View {
    let user: User
    var body: some View {
        VStack {
            ProfileHeader(user: user)
            ProfileStats(user: user)
        }
    }
}
```

## Common mistakes

- One massive `body` instead of extracted subviews.
- Looking for UIKit-style base classes.

## Related concepts

- [Reusable Views](/concepts/reusable_views.md)
- [Containers](/concepts/containers.md)
