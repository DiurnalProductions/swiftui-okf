---
id: swiftui.cancellation
type: concept
title: Cancellation
description: Cancel async work when views disappear or task identifiers change.
tags: [swiftui, concurrency, async]
prerequisites:
  - swiftui.task_modifier
  - swift.async_await
related:
  - swiftui.async_data_loading
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Swift concurrency tasks started by `.task` cancel when views leave the hierarchy. Check `Task.isCancelled` in long loops.

## Mental model

Cancellation is **cooperative**. When a user navigates away, in-flight fetches should stop to avoid wasted work and stale UI updates.

## Example

```swift
.task {
    for try await event in stream {
        guard !Task.isCancelled else { return }
        handle(event)
    }
}
```

## Common mistakes

- Ignoring cancellation and updating state after view disappears.
- Unstructured tasks that outlive their views.

## Related concepts

- [.task Modifier](/concepts/task_modifier.md)
