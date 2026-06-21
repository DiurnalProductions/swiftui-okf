---
id: swiftui.data_flow
type: concept
title: Data Flow
description: SwiftUI uses unidirectional data flow: state flows down the view tree, user actions flow up.
tags: [swiftui, state, architecture]
prerequisites:
  - swiftui.views
related:
  - swiftui.source_of_truth
  - swiftui.binding
  - swiftui.environment
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

SwiftUI apps follow **unidirectional data flow**. Parents own data and pass read-only values or bindings to children. Children send actions upward via closures or binding writes.

## Mental model

Draw arrows **down** for data and **up** for events. State ownership should form a clear tree, not a web of mutual references.

Lift shared state to the lowest common ancestor or inject via environment.

## Example

```swift
struct ParentView: View {
    @State private var text = ""
    var body: some View {
        TextField("Enter text", text: $text)
    }
}
```

## Common mistakes

- Passing bindings when children only need to read.
- Using `@EnvironmentObject` to avoid designing ownership.
- Mutating shared models without proper observation.

## Related concepts

- [Source of Truth](/concepts/source_of_truth.md)
- [@Binding](/concepts/binding.md)
