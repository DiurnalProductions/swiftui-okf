---
id: swiftui.swiftdata_concepts
type: concept
title: SwiftData Concepts
description: High-level overview of SwiftData persistence with @Model and @Query in SwiftUI.
tags: [swiftui, persistence, swiftdata]
prerequisites:
  - swiftui.observable
  - swiftui.app_storage
related:
  - swiftui.source_of_truth
  - swiftui.dependency_injection
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

SwiftData provides `@Model` classes persisted automatically. `@Query` in SwiftUI fetches models and updates views when data changes.

## Mental model

SwiftData is the **declarative persistence layer**. Models are reference types; `@Query` replaces manual fetch + refresh logic.

## Example

```swift
@Query(sort: \Item.name) private var items: [Item]

var body: some View {
    List(items) { Text($0.name) }
}
```

## Common mistakes

- Treating this pack as exhaustive SwiftData documentation.
- Mixing duplicate in-memory state with `@Query` results.

## Related concepts

- [@Observable](/concepts/observable.md)
