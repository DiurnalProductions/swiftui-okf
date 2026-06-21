---
id: swiftui.modifiers
type: concept
title: Modifiers
description: View modifiers wrap a view and return a new view value, transforming appearance or behavior.
tags: [swiftui, composition, fundamentals]
prerequisites:
  - swiftui.views
related:
  - swiftui.diffing
  - swiftui.themes_appearance
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Modifiers chain methods that **wrap** views and return new view values. They do not mutate — order matters.

## Mental model

Each modifier is a **new layer** in the view tree. `.padding().background()` differs from `.background().padding()`.

## Example

```swift
Text("Hello")
    .font(.title)
    .padding()
    .background(.ultraThinMaterial, in: RoundedRectangle(cornerRadius: 12))
```

## Common mistakes

- Assuming modifiers mutate in place.
- Wrong modifier order causing layout surprises.

## Related concepts

- [Diffing and Reconciliation](/concepts/diffing.md)
- [Themes and Appearance](/concepts/themes_appearance.md)
