---
id: swiftui.app_storage
type: concept
title: AppStorage
description: UserDefaults-backed persistent property wrapper for simple app settings.
tags: [swiftui, persistence, state]
prerequisites:
  - swiftui.state
  - swiftui.source_of_truth
related:
  - swiftui.scene_storage
  - swiftui.swiftdata_concepts
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`@AppStorage` reads and writes UserDefaults keys, persisting simple settings (booleans, strings, numbers) across launches.

## Mental model

AppStorage is **persistent @State** for primitive preferences. Source of truth shifts to UserDefaults; views react to changes.

## Example

```swift
@AppStorage("isDarkMode") private var isDarkMode = false
```

## Common mistakes

- Storing large blobs or relational data — use SwiftData or files.
- Key string typos causing silent separate storage.

## Related concepts

- [SceneStorage](/concepts/scene_storage.md)
