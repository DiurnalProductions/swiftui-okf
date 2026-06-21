---
id: swiftui.views
type: concept
title: Views as Functions of State
description: SwiftUI views are value types that describe UI for a given state, not persistent on-screen objects.
tags: [swiftui, declarative, fundamentals]
prerequisites:
  - swift.structures
  - swift.protocols
related:
  - swiftui.body_recomputation
  - swiftui.composition
  - swiftui.data_flow
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

A SwiftUI `View` is a protocol adopted by structs whose job is to describe user interface. The `body` property returns a view tree representing what should appear on screen **right now**, given the current state. Views are ephemeral: they are created, evaluated, and discarded constantly.

## Mental model

Think of a view as a **pure function**: `UI = f(state)`. You never call methods on a view to change its appearance. Instead, you change state, and SwiftUI calls `body` again to get a fresh description.

Views are **value types** (typically structs). They do not correspond 1:1 with UIKit views. A single `Text` struct in your code may be recreated hundreds of times per second during animation.

Do not store views in properties or mutate them. Describe, don't manipulate.

## Example

```swift
struct GreetingView: View {
    let name: String

    var body: some View {
        Text("Hello, \(name)")
            .font(.title)
    }
}
```

When `name` changes, SwiftUI re-evaluates `body` and updates the display.

## Common mistakes

- Treating views like UIKit objects you configure once and mutate later.
- Putting business logic inside `body` instead of in a model or action handler.
- Assuming a view instance persists across renders — it does not.

## Related concepts

- [Body Recomputation](/concepts/body_recomputation.md)
- [Data Flow](/concepts/data_flow.md)
- [Composition Over Inheritance](/concepts/composition.md)
