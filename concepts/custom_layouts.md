---
id: swiftui.custom_layouts
type: concept
title: Custom Layouts
description: The Layout protocol enables bespoke arrangement of child views beyond built-in stacks.
tags: [swiftui, layout, advanced]
prerequisites:
  - swiftui.geometry_reader
  - swiftui.vstack
  - swiftui.hstack
related:
  - swiftui.containers
  - swiftui.frame
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Custom layouts conform to `Layout`, implementing `sizeThatFits` and `placeSubviews`. Use for flow layouts, radial menus, or bespoke grids.

## Mental model

Custom layouts participate in the same **negotiation protocol** as stacks but with your placement logic. Prefer built-in stacks until they are insufficient.

## Example

```swift
struct FlowLayout: Layout {
    func sizeThatFits(proposal: ProposedViewSize, subviews: Subviews, cache: inout ()) -> CGSize { /* ... */ }
    func placeSubviews(in bounds: CGRect, proposal: ProposedViewSize, subviews: Subviews, cache: inout ()) { /* ... */ }
}
```

## Common mistakes

- Building custom layouts when `LazyVGrid` or stacks would work.
- Ignoring cache parameter for expensive measurements.

## Related concepts

- [GeometryReader](/concepts/geometry_reader.md)
- [Grids](/concepts/grids.md)
