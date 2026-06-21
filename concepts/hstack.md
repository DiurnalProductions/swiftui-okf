---
id: swiftui.hstack
type: concept
title: HStack
description: A horizontal stack container that arranges child views left to right.
tags: [swiftui, layout, stack]
prerequisites:
  - swiftui.containers
  - swiftui.alignment
related:
  - swiftui.vstack
  - swiftui.spacer
  - swiftui.lazy_hstack
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

An `HStack` arranges children horizontally. Useful for toolbars, label-value pairs, and inline controls.

## Mental model

Children share the **height** of the tallest child. Width is the sum of children. `Spacer()` distributes horizontal space.

## Example

```swift
HStack {
    Image(systemName: "star.fill")
    Text("Featured")
    Spacer()
    Text("99")
}
```

## Common mistakes

- Forgetting `Spacer()` when pushing trailing content.
- Putting too many items without wrapping or scrolling.

## Related concepts

- [VStack](/concepts/vstack.md)
- [Alignment](/concepts/alignment.md)
