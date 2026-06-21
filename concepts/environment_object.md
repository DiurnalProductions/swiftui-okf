---
id: swiftui.environment_object
type: concept
title: @EnvironmentObject
description: Inject and retrieve shared observable models anywhere in the subtree without explicit passing.
tags: [swiftui, state, environment]
prerequisites:
  - swiftui.observable
  - swiftui.environment
related:
  - swiftui.dependency_injection
  - swiftui.mvvm
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`@EnvironmentObject` (legacy) or `@Environment(Type.self)` retrieves a shared model injected with `.environment(_:)`. Useful for app-wide session or settings.

## Mental model

Think of environment injection as a **service locator** for one model type in a subtree. Prefer initializer injection for testability.

## Example

```swift
@main
struct MyApp: App {
    @State private var session = SessionModel()
    var body: some Scene {
        WindowGroup {
            RootView().environment(session)
        }
    }
}
```

## Common mistakes

- Forgetting to inject above views that require it — runtime crash.
- Using environment for local parent-child data.

## Related concepts

- [@Observable](/concepts/observable.md)
- [Dependency Injection](/concepts/dependency_injection.md)
