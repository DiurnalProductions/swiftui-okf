---
id: swiftui.navigation_destinations
type: concept
title: Navigation Destinations
description: Type-safe destination views registered for values pushed onto a NavigationStack.
tags: [swiftui, navigation]
prerequisites:
  - swiftui.navigation_stack
related:
  - swiftui.sheet_presentation
  - swiftui.data_flow
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`.navigationDestination(for:destination:)` maps hashable value types to views. `NavigationLink(value:)` pushes those values.

## Mental model

Destinations are **declarative routes**. The stack holds data; SwiftUI resolves the view. Keeps navigation logic centralized.

## Example

```swift
.navigationDestination(for: UUID.self) { id in
    ItemDetailView(id: id)
}
```

## Common mistakes

- Registering destinations on the wrong level of the hierarchy.
- Using non-Hashable types for navigation values.

## Related concepts

- [NavigationStack](/concepts/navigation_stack.md)
