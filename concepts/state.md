---
id: swiftui.state
type: concept
title: @State
description: View-local mutable state owned privately by a view, persisted across body recomputations by identity.
tags: [swiftui, state, property-wrapper]
prerequisites:
  - swiftui.source_of_truth
related:
  - swiftui.binding
  - swiftui.app_storage
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`@State` wraps value-type storage that a view **owns privately**. SwiftUI allocates persistent storage keyed to view identity, surviving `body` recomputation.

## Mental model

`@State` is external storage managed by SwiftUI, not a struct property. Use it for UI-local ephemeral state. Use `@Observable` for complex domain models.

## Example

```swift
struct ToggleExample: View {
    @State private var isOn = false
    var body: some View {
        Toggle("Enable", isOn: $isOn)
    }
}
```

## Common mistakes

- Using `@State` for large domain models.
- Creating observable models inside `@State` in `body`.
- Expecting `@State` to reset on every `body` call.

## Related concepts

- [@Binding](/concepts/binding.md)
- [Source of Truth](/concepts/source_of_truth.md)
