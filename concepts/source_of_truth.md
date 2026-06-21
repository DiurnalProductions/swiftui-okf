---
id: swiftui.source_of_truth
type: concept
title: Source of Truth
description: Every piece of mutable state should have exactly one authoritative owner in the view hierarchy.
tags: [swiftui, state, architecture]
prerequisites:
  - swiftui.views
  - swiftui.data_flow
related:
  - swiftui.state
  - swiftui.observable
  - swiftui.state_ownership
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

The **single source of truth** principle: one place owns each mutable value; everyone else reads or binds to it. Duplicated state causes sync bugs.

## Mental model

Ask: **Who is responsible when this value changes?** That owner holds the canonical copy. Others receive `let`, `@Binding`, or observe via `@Observable`.

## Example

```swift
struct TodoList: View {
    @State private var todos: [Todo] = []
    var body: some View {
        ForEach(todos) { TodoRow(todo: $0) }
    }
}
```

## Common mistakes

- Copying model data into `@State` in multiple views.
- Creating `@Observable` models inside `body`.
- Storing derived data as separate mutable state.

## Related concepts

- [@State](/concepts/state.md)
- [State Ownership](/concepts/state_ownership.md)
