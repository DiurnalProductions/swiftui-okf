---
id: swiftui.modal_presentation
type: concept
title: Modal Presentation
description: Full-screen covers and custom presentation styles for immersive modal experiences.
tags: [swiftui, navigation, presentation]
prerequisites:
  - swiftui.sheet_presentation
related:
  - swiftui.navigation_stack
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`.fullScreenCover` and `.presentationDetents` (iOS) offer full-screen or partial-height modals beyond standard sheets.

## Mental model

Full-screen covers **replace** the current context visually. Use for onboarding, media viewers, or immersive flows.

## Example

```swift
.fullScreenCover(isPresented: $showCamera) {
    CameraView()
}
```

## Common mistakes

- Using fullScreenCover for simple forms — sheets are often enough.
- Forgetting dismiss environment in modal content.

## Related concepts

- [Sheet Presentation](/concepts/sheet_presentation.md)
