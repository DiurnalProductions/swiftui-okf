---
id: swiftui.reusable_views
type: concept
title: Reusable Views
description: Extract parameterized view structs for UI patterns used across multiple screens.
tags: [swiftui, composition, architecture]
prerequisites:
  - swiftui.views
  - swiftui.composition
related:
  - swiftui.binding
  - swiftui.modifiers
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Reusable views are focused structs with clear inputs: `let` data, `@Binding` for editable fields, closures for actions.

## Mental model

Reusable views are **parameterized UI functions**. Keep them dumb about navigation; emit events upward.

## Example

```swift
struct PrimaryButton: View {
    let title: String
    let action: () -> Void
    var body: some View {
        Button(title, action: action).buttonStyle(.borderedProminent)
    }
}
```

## Common mistakes

- Reusable views that fetch their own data.
- Hidden `@EnvironmentObject` in generic components.

## Related concepts

- [Composition Over Inheritance](/concepts/composition.md)
- [@Binding](/concepts/binding.md)
