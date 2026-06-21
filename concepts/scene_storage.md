---
id: swiftui.scene_storage
type: concept
title: SceneStorage
description: Restore transient UI state across scene sessions on a per-scene basis.
tags: [swiftui, persistence, state]
prerequisites:
  - swiftui.state
related:
  - swiftui.app_storage
  - swiftui.navigation_stack
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`@SceneStorage` persists lightweight UI restoration state (scroll positions, selected tabs) per scene, not globally.

## Mental model

SceneStorage is for **restoration**, not user preferences. System may discard it; don't store critical data.

## Example

```swift
@SceneStorage("selectedTab") private var selectedTab = 0
```

## Common mistakes

- Using SceneStorage for user settings — use AppStorage.
- Expecting persistence across app deletion/reinstall.

## Related concepts

- [AppStorage](/concepts/app_storage.md)
