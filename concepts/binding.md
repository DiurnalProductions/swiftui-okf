---
id: swiftui.binding
type: concept
title: @Binding
description: A two-way reference to state owned elsewhere, enabling child views to read and write parent state.
tags: [swiftui, state, property-wrapper]
prerequisites:
  - swiftui.state
related:
  - swiftui.data_flow
  - swiftui.reusable_views
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`@Binding` provides read-write access to state **owned by an ancestor**. Create bindings with `$` on `@State` or observable properties.

## Mental model

A binding is a **remote control** for someone else's state. Prefer `let` + action closures when children only send events.

## Example

```swift
struct SettingsRow: View {
    @Binding var username: String
    var body: some View {
        TextField("Username", text: $username)
    }
}
```

## Common mistakes

- Using `@Binding` when children should not mutate.
- Binding to computed properties without custom `Binding(get:set:)`.

## Related concepts

- [@State](/concepts/state.md)
- [Data Flow](/concepts/data_flow.md)
