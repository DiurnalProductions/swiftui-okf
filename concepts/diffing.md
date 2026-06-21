---
id: swiftui.diffing
type: concept
title: Diffing and Reconciliation
description: SwiftUI compares successive view trees and applies minimal changes to the platform render tree.
tags: [swiftui, declarative, rendering]
prerequisites:
  - swiftui.identity
  - swiftui.body_recomputation
related:
  - swiftui.implicit_animations
  - swiftui.modifiers
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

After `body` produces a new view description, SwiftUI **diffs** it against the previous description. Matching nodes update in place; new nodes insert; removed nodes tear down.

## Mental model

Picture two snapshots of a tree. SwiftUI walks both in parallel, matching by identity and type. Matched nodes compare inputs (text, colors, frames). Only changed inputs propagate to the platform layer.

Modifiers form nodes in this tree — order and values affect diff results.

## Example

```swift
if isExpanded {
    DetailView()
} else {
    SummaryView()
}
// Different types at same position = identity change
```

## Common mistakes

- Swapping view types with `if/else` and expecting `@State` to persist.
- Reordering modifiers thinking they mutate in place.
- Overusing `AnyView`, erasing type information.

## Related concepts

- [View Identity](/concepts/identity.md)
- [Implicit Animations](/concepts/implicit_animations.md)
