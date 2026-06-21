---
id: swiftui.foreach
type: concept
title: ForEach
description: Iterate collections into views with stable identity for efficient diffing.
tags: [swiftui, collections]
prerequisites:
  - swiftui.views
  - swiftui.identity
related:
  - swiftui.list
  - swiftui.lazy_vstack
  - swiftui.grids
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`ForEach` generates views from a collection using identifiable or explicit `id` key paths. Identity drives diffing in dynamic lists.

## Mental model

ForEach is **map for views**. Each element becomes a child view. Stable IDs are critical for performance and correct `@State` in rows.

## Example

```swift
ForEach(todos) { todo in
    TodoRow(todo: todo)
}
```

## Common mistakes

- Using array indices as IDs when data mutates.
- Non-unique IDs causing undefined diff behavior.

## Related concepts

- [View Identity](/concepts/identity.md)
- [List](/concepts/list.md)
