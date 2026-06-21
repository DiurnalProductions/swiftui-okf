---
id: swiftui.vstack
type: concept
title: VStack
description: A vertical stack container that arranges child views top to bottom.
tags: [swiftui, layout, stack]
prerequisites:
  - swiftui.containers
  - swiftui.alignment
related:
  - swiftui.hstack
  - swiftui.spacer
  - swiftui.lazy_vstack
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

A `VStack` arranges children vertically along the Y axis. Control alignment with the `alignment` parameter and spacing between children.

## Mental model

Children share the **width** of the widest child (by default). Height is the sum of children plus spacing. Use `Spacer()` to push content apart vertically.

## Example

```swift
VStack(alignment: .leading, spacing: 12) {
    Text("Title")
    Text("Body copy")
    Spacer()
    Button("Continue") {}
}
```

## Common mistakes

- Expecting children to fill width without `.frame(maxWidth: .infinity)`.
- Nesting many VStacks without considering ScrollView for overflow.

## Related concepts

- [HStack](/concepts/hstack.md)
- [Spacer](/concepts/spacer.md)
