---
id: swiftui.list
type: concept
title: List
description: Platform-native scrollable list with rows, sections, selection, and editing.
tags: [swiftui, collections]
prerequisites:
  - swiftui.foreach
related:
  - swiftui.lazy_vstack
  - swiftui.navigation_stack
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`List` renders scrollable rows with platform styling, swipe actions, sections, and selection. Backed by UITableView/NSOutlineView on some platforms.

## Mental model

List is **ForEach plus platform chrome** — separators, inset grouping, edit mode. Prefer List for settings-style UI; lazy stacks for custom layouts.

## Example

```swift
List(items) { item in
    Text(item.title)
}
```

## Common mistakes

- Putting heavy custom layout inside List rows without lazy consideration.
- Using List when a simple ScrollView + LazyVStack is clearer.

## Related concepts

- [ForEach](/concepts/foreach.md)
- [LazyVStack](/concepts/lazy_vstack.md)
