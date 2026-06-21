---
id: swiftui.state_ownership
type: concept
title: State Ownership
description: Architectural decisions about where state lives in the view hierarchy.
tags: [swiftui, architecture, state]
prerequisites:
  - swiftui.source_of_truth
  - swiftui.data_flow
related:
  - swiftui.mvvm
  - swiftui.dependency_injection
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

State ownership determines maintainability. Lift state to the lowest common ancestor, inject shared models, keep leaf views stateless where possible.

## Mental model

Draw a **state map**: who owns what? Views should either own local UI state, receive data, or observe shared models — not all three ambiguously.

## Example

```swift
// Coordinator owns navigation + model
struct FeatureFlow: View {
    @State private var path = NavigationPath()
    @State private var model = FeatureModel()
    // ...
}
```

## Common mistakes

- Every view creating its own copy of shared data.
- God-object `@Observable` holding unrelated state.

## Related concepts

- [Source of Truth](/concepts/source_of_truth.md)
- [MVVM in SwiftUI](/concepts/mvvm.md)
