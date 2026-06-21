---
id: swiftui.zstack
type: concept
title: ZStack
description: A depth stack that overlays child views on the Z axis, back to front.
tags: [swiftui, layout, stack]
prerequisites:
  - swiftui.containers
  - swiftui.alignment
related:
  - swiftui.vstack
  - swiftui.frame
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

A `ZStack` layers children centered (by default) on top of each other. Later children appear in front.

## Mental model

Think **stack of transparent sheets**. Size defaults to the largest child. Use `alignment` to pin overlays to edges.

## Example

```swift
ZStack(alignment: .topTrailing) {
    Image("photo").resizable().scaledToFill()
    Button("Save") { }.padding()
}
```

## Common mistakes

- Using `ZStack` for side-by-side layout — use `HStack`.
- Forgetting clipping on full-bleed background images.

## Related concepts

- [Alignment](/concepts/alignment.md)
- [Frame Behavior](/concepts/frame.md)
