---
id: swiftui.separation_of_concerns
type: concept
title: Separation of Concerns
description: Keep views thin, models focused, and services responsible for side effects.
tags: [swiftui, architecture]
prerequisites:
  - swiftui.composition
  - swiftui.state_ownership
related:
  - swiftui.mvvm
  - swiftui.dependency_injection
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Views describe UI. Models hold state and domain logic. Services perform I/O. Avoid networking and persistence directly in `body`.

## Mental model

Each layer has one job. Views **render and route events**. They don't parse JSON or manage URL sessions.

## Example

```swift
// View dispatches intent
Button("Save") { await model.save() }

// Model coordinates
@Observable class EditorModel {
    func save() async { await repository.persist(draft) }
}
```

## Common mistakes

- Massive views with networking, parsing, and layout intertwined.
- Models that import SwiftUI and return `some View`.

## Related concepts

- [MVVM in SwiftUI](/concepts/mvvm.md)
