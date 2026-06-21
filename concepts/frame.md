---
id: swiftui.frame
type: concept
title: Frame Behavior
description: How views propose and accept sizes through frame modifiers and layout constraints.
tags: [swiftui, layout]
prerequisites:
  - swiftui.containers
  - swiftui.alignment
related:
  - swiftui.geometry_reader
  - swiftui.spacer
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

The `.frame()` modifier sets ideal, minimum, maximum, or fixed sizes and alignment within proposed space.

## Mental model

Layout is **negotiation**: parent proposes, child responds with its size, parent assigns origin. `.frame(maxWidth: .infinity)` makes a view expand.

## Example

```swift
Text("Hello")
    .frame(maxWidth: .infinity, minHeight: 44, alignment: .leading)
```

## Common mistakes

- Setting fixed frames on content that should adapt.
- Expecting `.frame(width:height:)` to scale content — it only sets layout box.

## Related concepts

- [GeometryReader](/concepts/geometry_reader.md)
- [Alignment](/concepts/alignment.md)
