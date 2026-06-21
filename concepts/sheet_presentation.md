---
id: swiftui.sheet_presentation
type: concept
title: Sheet Presentation
description: Present modal sheets that slide up from the bottom for focused tasks.
tags: [swiftui, navigation, presentation]
prerequisites:
  - swiftui.views
related:
  - swiftui.modal_presentation
  - swiftui.state
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

The `.sheet(isPresented:)` or `.sheet(item:)` modifier presents a modal child view. Use `@Environment(\.dismiss)` to close.

## Mental model

Sheets are **temporary branches** of the UI tree. Boolean or optional item state controls presentation. Content gets its own environment subtree.

## Example

```swift
.sheet(isPresented: $showSettings) {
    SettingsView()
}
```

## Common mistakes

- Presenting sheets without state ownership — who sets `isPresented`?
- Nesting too many sheets deep.

## Related concepts

- [Modal Presentation](/concepts/modal_presentation.md)
