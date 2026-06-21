---
id: swiftui.themes_appearance
type: concept
title: Themes and Appearance
description: Color scheme, typography, and styling through environment and modifiers.
tags: [swiftui, environment, styling]
prerequisites:
  - swiftui.environment_values
related:
  - swiftui.modifiers
  - swiftui.environment
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

SwiftUI adapts to light/dark mode via `@Environment(\.colorScheme)`. Prefer semantic colors (`.primary`, `.secondary`) and system fonts.

## Mental model

Theme is **environment-driven appearance**. Custom design systems wrap modifiers or use environment keys for tokens.

## Example

```swift
Text("Title")
    .foregroundStyle(.primary)
    .font(.headline)
```

## Common mistakes

- Hard-coded colors that don't adapt to dark mode.
- Fighting system appearance instead of embracing semantic styles.

## Related concepts

- [Modifiers](/concepts/modifiers.md)
- [Environment Values](/concepts/environment_values.md)
