---
id: swiftui.body_recomputation
type: concept
title: Body Recomputation
description: SwiftUI re-evaluates a view's body whenever its dependencies change, producing a new view tree for reconciliation.
tags: [swiftui, declarative, rendering]
prerequisites:
  - swiftui.views
related:
  - swiftui.identity
  - swiftui.diffing
  - swiftui.implicit_animations
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Every time a view's state dependencies change, SwiftUI **re-invokes `body`**, producing a brand-new tree of view values. The framework diffs this tree against the previous one and applies minimal updates to the platform render tree.

## Mental model

Imagine `body` as a **template function** that runs on every relevant change. It should be fast and side-effect-free. Heavy computation belongs in models or cached properties outside `body`.

Recomputation is **not** the same as redrawing the entire screen. SwiftUI uses identity and diffing to update only what changed.

## Example

```swift
struct CounterView: View {
    @State private var count = 0

    var body: some View {
        VStack {
            Text("Count: \(count)")
            Button("Increment") { count += 1 }
        }
    }
}
```

## Common mistakes

- Performing side effects inside `body` (API calls, state mutations).
- Assuming `body` runs only once per view lifetime.
- Expensive work in `body` without caching.

## Related concepts

- [View Identity](/concepts/identity.md)
- [Diffing and Reconciliation](/concepts/diffing.md)
