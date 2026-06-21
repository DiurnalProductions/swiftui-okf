---
id: swiftui.environment_values
type: concept
title: Environment Values
description: Typed key-value storage propagated through the view tree via EnvironmentValues.
tags: [swiftui, environment]
prerequisites:
  - swiftui.data_flow
  - swiftui.views
related:
  - swiftui.environment
  - swiftui.dependency_propagation
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`EnvironmentValues` holds system and custom keys (color scheme, locale, model context). Access with `@Environment(\.keyPath)`.

## Mental model

Environment values are **implicit parameters** flowing down the tree. Child views read; ancestors inject with `.environment(_:_:)`.

## Example

```swift
@Environment(\.locale) private var locale
@Environment(\.modelContext) private var modelContext
```

## Common mistakes

- Custom keys without `EnvironmentKey` conformance.
- Overriding environment too high or too low in tree.

## Related concepts

- [@Environment](/concepts/environment.md)
