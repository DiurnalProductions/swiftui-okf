---
id: swiftui.alignment
type: concept
title: Alignment
description: How child views are positioned within stacks, frames, and overlays.
tags: [swiftui, layout]
prerequisites:
  - swiftui.containers
related:
  - swiftui.vstack
  - swiftui.frame
  - swiftui.zstack
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Alignment controls positioning on the cross-axis of stacks and within frames. SwiftUI provides built-in alignments like `.leading`, `.center`, `.topTrailing`.

## Mental model

In a `VStack`, alignment is **horizontal** (cross-axis). In an `HStack`, alignment is **vertical**. Custom alignments use `Alignment` guides.

## Example

```swift
VStack(alignment: .leading) {
    Text("Title")
    Text("Subtitle")
}
.frame(maxWidth: .infinity, alignment: .leading)
```

## Common mistakes

- Confusing stack alignment with frame alignment.
- Expecting `.center` to fill available width.

## Related concepts

- [VStack](/concepts/vstack.md)
- [Frame Behavior](/concepts/frame.md)
