---
id: swiftui.navigation_stack
type: concept
title: NavigationStack
description: Path-based stack navigation for pushing and popping hierarchical destinations.
tags: [swiftui, navigation]
prerequisites:
  - swiftui.views
related:
  - swiftui.navigation_destinations
  - swiftui.data_flow
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`NavigationStack` manages a stack of views with programmatic navigation via `NavigationPath` or bound paths. Replaces deprecated `NavigationView`.

## Mental model

NavigationStack is a **stack of screens**. State drives the path; pushing appends, popping removes. SwiftUI builds only visible destinations.

## Example

```swift
NavigationStack {
    List(items) { item in
        NavigationLink(value: item) { Text(item.name) }
    }
    .navigationDestination(for: Item.self) { item in
        DetailView(item: item)
    }
}
```

## Common mistakes

- Mixing old `NavigationView` patterns with `NavigationStack`.
- Not binding navigation state for deep linking.

## Related concepts

- [Navigation Destinations](/concepts/navigation_destinations.md)
