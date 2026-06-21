---
id: swiftui.task_modifier
type: concept
title: .task Modifier
description: Structured async work tied to view lifetime, starting when a view appears.
tags: [swiftui, concurrency, async]
prerequisites:
  - swiftui.async_data_loading
  - swiftui.views
related:
  - swiftui.cancellation
  - swiftui.main_actor
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

The `.task` modifier runs an async closure when the view appears and **automatically cancels** it when the view disappears.

## Mental model

`.task` replaces fragile `onAppear { Task { } }` patterns with lifecycle-aware async work.

## Example

```swift
.task {
    items = await repository.fetchItems()
}
.task(id: userID) {
    profile = await loadProfile(userID)
}
```

## Common mistakes

- Using `onAppear` + unstructured `Task` without cancellation.
- Heavy work in `.task` without `id:` when inputs change.

## Related concepts

- [Cancellation](/concepts/cancellation.md)
