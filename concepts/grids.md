---
id: swiftui.grids
type: concept
title: Grids
description: LazyVGrid and LazyHGrid arrange content in flexible grid layouts.
tags: [swiftui, collections, layout]
prerequisites:
  - swiftui.foreach
  - swiftui.lazy_vstack
related:
  - swiftui.custom_layouts
  - swiftui.list
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Grids use `GridItem` configurations (fixed, flexible, adaptive) to define columns or rows. Lazy variants load on scroll.

## Mental model

Grids are **two-dimensional lazy stacks**. `GridItem(.adaptive(minimum:))` creates as many columns as fit.

## Example

```swift
LazyVGrid(columns: [GridItem(.adaptive(minimum: 150))]) {
    ForEach(items) { ItemTile(item: $0) }
}
```

## Common mistakes

- Non-lazy Grid for large datasets.
- Wrong GridItem mix causing uneven column widths.

## Related concepts

- [LazyVStack](/concepts/lazy_vstack.md)
- [Custom Layouts](/concepts/custom_layouts.md)
