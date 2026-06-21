---
id: swiftui.environment
type: concept
title: @Environment
description: Read values propagated implicitly through the view hierarchy without explicit parameter passing.
tags: [swiftui, state, environment]
prerequisites:
  - swiftui.data_flow
  - swiftui.environment_values
related:
  - swiftui.environment_object
  - swiftui.dependency_injection
  - swiftui.themes_appearance
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`@Environment` reads **environment values** injected by ancestors or the system. Use `@Environment(\.keyPath)` for typed access.

## Mental model

Environment is **implicit context** for views. System values (`.colorScheme`, `.dismiss`) and custom values share the same mechanism.

## Example

```swift
struct ContentView: View {
    @Environment(\.colorScheme) private var colorScheme
    var body: some View {
        Text(colorScheme == .dark ? "Dark" : "Light")
    }
}
```

## Common mistakes

- Using environment for data that should be explicit parameters.
- Confusing `@Environment` with `@EnvironmentObject`.

## Related concepts

- [Environment Values](/concepts/environment_values.md)
- [Dependency Injection](/concepts/dependency_injection.md)
