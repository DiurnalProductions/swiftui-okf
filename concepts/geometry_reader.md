---
id: swiftui.geometry_reader
type: concept
title: GeometryReader
description: A container that reads the size and coordinate space proposed by its parent.
tags: [swiftui, layout]
prerequisites:
  - swiftui.frame
related:
  - swiftui.custom_layouts
  - swiftui.matched_geometry_effect
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`GeometryReader` provides a `GeometryProxy` with `size`, `safeAreaInsets`, and coordinate conversion. It expands to fill available space by default.

## Mental model

Use GeometryReader when layout depends on **available space** — proportional sizing, parallax, custom positioning. It is greedy: it takes all space offered.

## Example

```swift
GeometryReader { geo in
    Rectangle()
        .fill(.blue)
        .frame(width: geo.size.width * 0.5)
}
```

## Common mistakes

- Overusing GeometryReader where stacks and frames suffice.
- Forgetting it expands to fill parent — breaks intrinsic sizing.

## Related concepts

- [Custom Layouts](/concepts/custom_layouts.md)
- [Frame Behavior](/concepts/frame.md)
