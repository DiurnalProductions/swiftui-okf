---
id: swiftui.matched_geometry_effect
type: concept
title: Matched Geometry Effect
description: Shared-element transitions that morph views between two positions using a namespace ID.
tags: [swiftui, animation, advanced]
prerequisites:
  - swiftui.explicit_animations
  - swiftui.identity
related:
  - swiftui.transitions
  - swiftui.geometry_reader
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`.matchedGeometryEffect(id:in:)` links two views across states so SwiftUI animates frame and appearance between them.

## Mental model

Matched geometry creates a **visual bridge** between views that represent the same entity in different layouts (hero animations).

## Example

```swift
@Namespace private var ns

if expanded {
    Image("photo").matchedGeometryEffect(id: "photo", in: ns)
} else {
    Thumbnail().matchedGeometryEffect(id: "photo", in: ns)
}
```

## Common mistakes

- Mismatched IDs or namespaces.
- Using without `withAnimation` — jump cuts instead of morph.

## Related concepts

- [View Identity](/concepts/identity.md)
- [Explicit Animations](/concepts/explicit_animations.md)
