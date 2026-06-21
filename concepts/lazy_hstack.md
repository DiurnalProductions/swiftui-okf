---
id: swiftui.lazy_hstack
type: concept
title: LazyHStack
description: Horizontally lazy-loaded stack for performant horizontal scrolling content.
tags: [swiftui, collections, layout]
prerequisites:
  - swiftui.hstack
  - swiftui.foreach
related:
  - swiftui.lazy_vstack
  - swiftui.grids
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`LazyHStack` lazily loads horizontal content inside a horizontal `ScrollView`.

## Mental model

Same lazy semantics as LazyVStack but on the **horizontal axis** — carousels, timeline strips.

## Example

```swift
ScrollView(.horizontal) {
    LazyHStack(spacing: 12) {
        ForEach(items) { ItemThumbnail(item: $0) }
    }
}
```

## Common mistakes

- Forgetting horizontal ScrollView wrapper.
- Using for small fixed item counts — regular HStack is simpler.

## Related concepts

- [LazyVStack](/concepts/lazy_vstack.md)
