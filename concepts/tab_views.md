---
id: swiftui.tab_views
type: concept
title: Tab Views
description: TabView provides top-level section switching with persistent tab bar navigation.
tags: [swiftui, navigation]
prerequisites:
  - swiftui.views
related:
  - swiftui.navigation_stack
  - swiftui.state
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`TabView` switches between root-level sections, each typically containing its own navigation hierarchy. Selection can be bound with `@State`.

## Mental model

Tabs are **parallel root contexts**, not a push stack. Each tab maintains its own state when using `@State` inside tab content.

## Example

```swift
TabView(selection: $selectedTab) {
    HomeView().tabItem { Label("Home", systemImage: "house") }.tag(0)
    SettingsView().tabItem { Label("Settings", systemImage: "gear") }.tag(1)
}
```

## Common mistakes

- Deep navigation inside tabs without nested NavigationStacks.
- Too many tabs on iPhone — consider sidebar on iPad/macOS.

## Related concepts

- [NavigationStack](/concepts/navigation_stack.md)
