---
id: swiftui.spacer
type: concept
title: Spacer
description: Flexible empty space that expands along the stack axis to absorb available room.
tags: [swiftui, layout]
prerequisites:
  - swiftui.vstack
related:
  - swiftui.frame
  - swiftui.hstack
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

A `Spacer` expands to fill available space in a stack, pushing siblings apart.

## Mental model

Spacer is a **spring** — it takes all extra room on its axis. Multiple spacers share space equally.

## Example

```swift
HStack {
    Text("Left")
    Spacer()
    Text("Right")
}
```

## Common mistakes

- Using Spacer outside a stack — has no effect.
- Multiple spacers when fixed spacing (`spacing:`) would suffice.

## Related concepts

- [VStack](/concepts/vstack.md)
- [Frame Behavior](/concepts/frame.md)
