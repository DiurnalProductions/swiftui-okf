---
id: swiftui.containers
type: concept
title: Containers
description: Layout containers group child views and define how they are arranged on screen.
tags: [swiftui, layout, composition]
prerequisites:
  - swiftui.views
  - swiftui.composition
related:
  - swiftui.vstack
  - swiftui.hstack
  - swiftui.zstack
  - swiftui.alignment
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Containers — stacks, `Group`, `Section`, `Form` — hold child views and participate in layout negotiation.

## Mental model

Containers are **layout negotiators**: parent proposes space, children report ideal sizes, parent assigns frames.

## Example

```swift
VStack(alignment: .leading, spacing: 8) {
    Text("Title").font(.headline)
    Text("Subtitle").font(.subheadline)
}
```

## Common mistakes

- Excessive stack nesting without spacers or frames.
- Using `ZStack` when overlay would be clearer.

## Related concepts

- [VStack](/concepts/vstack.md)
- [Alignment](/concepts/alignment.md)
