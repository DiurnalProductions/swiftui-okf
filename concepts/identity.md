---
id: swiftui.identity
type: concept
title: View Identity
description: View identity tells SwiftUI whether two view values represent the same logical element across body recomputations.
tags: [swiftui, declarative, rendering]
prerequisites:
  - swiftui.views
  - swiftui.body_recomputation
related:
  - swiftui.diffing
  - swiftui.foreach
  - swiftui.matched_geometry_effect
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

When `body` produces a new view tree, SwiftUI must decide whether a view is the **same** element as before or a **new** one. Identity comes from structural position in the tree or explicit `.id(_:)` / `ForEach` identifiers.

## Mental model

Identity is a **stable name tag** on a seat. Preserved identity means `@State` survives recomputation. Changed identity resets state, breaks animations, and loses focus.

In lists, unstable IDs cause wrong-row updates and leaked cell state.

## Example

```swift
ForEach(items) { item in
    RowView(item: item)
        .id(item.id)
}
```

## Common mistakes

- Using array index as `ForEach` identity when items reorder.
- Applying `.id()` with frequently changing values.
- Swapping view types with `if/else` at the same structural position.

## Related concepts

- [Diffing and Reconciliation](/concepts/diffing.md)
- [ForEach](/concepts/foreach.md)
