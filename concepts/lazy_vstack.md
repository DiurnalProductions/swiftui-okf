---
id: swiftui.lazy_vstack
type: concept
title: LazyVStack
description: Vertically lazy-loaded stack that creates views only when they become visible.
tags: [swiftui, collections, layout]
prerequisites:
  - swiftui.vstack
  - swiftui.foreach
related:
  - swiftui.lazy_hstack
  - swiftui.grids
  - swiftui.list
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`LazyVStack` inside a `ScrollView` creates child views on demand as they scroll into view.

## Mental model

Lazy stacks **defer construction** — essential for large datasets. Non-lazy stacks create all children immediately.

## Example

```swift
ScrollView {
    LazyVStack(spacing: 16) {
        ForEach(items) { ItemCard(item: $0) }
    }
}
```

## Common mistakes

- Using LazyVStack without ScrollView — loads all anyway.
- Expecting `@State` in off-screen cells to stay initialized.

## Related concepts

- [LazyHStack](/concepts/lazy_hstack.md)
- [Grids](/concepts/grids.md)
