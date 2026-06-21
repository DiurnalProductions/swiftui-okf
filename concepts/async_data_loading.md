---
id: swiftui.async_data_loading
type: concept
title: Async Data Loading
description: Load remote or expensive data asynchronously and publish results to drive UI updates.
tags: [swiftui, concurrency, async]
prerequisites:
  - swiftui.main_actor
  - swiftui.observable
related:
  - swiftui.task_modifier
  - swiftui.cancellation
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Fetch data with `async/await`, then assign to `@State` or `@Observable` properties on the MainActor. Show loading and error states declaratively.

## Mental model

Loading is **state**: `.idle`, `.loading`, `.loaded`, `.failed`. The view is a function of loading state — spinner, content, or error.

## Example

```swift
@State private var items: [Item] = []
@State private var isLoading = true

var body: some View {
    Group {
        if isLoading { ProgressView() }
        else { List(items) { Text($0.name) } }
    }
}
```

## Common mistakes

- No loading or error UI states.
- Fetching in `body` or `onAppear` without structured cancellation.

## Related concepts

- [.task Modifier](/concepts/task_modifier.md)
