---
id: swiftui.dependency_propagation
type: concept
title: Dependency Propagation
description: How dependencies flow implicitly through the environment without explicit parameter drilling.
tags: [swiftui, environment, architecture]
prerequisites:
  - swiftui.environment_values
related:
  - swiftui.dependency_injection
  - swiftui.environment
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Environment propagates dependencies to all descendants. Override at any level to scope changes to subtrees.

## Mental model

Propagation is **broadcast down**. Siblings don't see each other's overrides. Useful for theme, locale, and shared services.

## Example

```swift
ContentView()
    .environment(\.apiClient, liveClient)
```

## Common mistakes

- Relying on environment for testability without preview overrides.
- Propagating frequently changing values — causes broad recomputation.

## Related concepts

- [Dependency Injection](/concepts/dependency_injection.md)
