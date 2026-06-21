---
id: swiftui.main_actor
type: concept
title: MainActor
description: UI-related code must run on the main actor; SwiftUI view bodies are main-actor isolated.
tags: [swiftui, concurrency, async]
prerequisites:
  - swift.async_await
related:
  - swiftui.async_data_loading
  - swiftui.task_modifier
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

SwiftUI views and `@Observable` UI models should mutate on `@MainActor`. Background work uses `async` functions off the main thread.

## Mental model

MainActor is the **UI thread contract**. Fetch on background, assign to `@State` or models on MainActor.

## Example

```swift
@MainActor
func loadData() async {
    let data = await fetchFromNetwork()
    self.items = data
}
```

## Common mistakes

- Updating `@State` from background threads — data races and warnings.
- Blocking MainActor with synchronous network calls.

## Related concepts

- [Async Data Loading](/concepts/async_data_loading.md)
