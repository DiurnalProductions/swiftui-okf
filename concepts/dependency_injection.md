---
id: swiftui.dependency_injection
type: concept
title: Dependency Injection
description: Provide services and models via initializers or environment instead of hard-coded singletons.
tags: [swiftui, architecture]
prerequisites:
  - swiftui.environment
  - swiftui.separation_of_concerns
related:
  - swiftui.environment_object
  - swiftui.mvvm
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

Inject dependencies through view initializers for explicit contracts, or environment for cross-cutting services (API client, analytics).

## Mental model

Injection enables **testing and swapping**. Previews pass mock dependencies; production passes live services.

## Example

```swift
struct ItemList: View {
    let repository: ItemRepository
    var body: some View { /* use repository */ }
}
```

## Common mistakes

- Hidden singletons accessed globally from views.
- Environment for values that should be explicit parameters.

## Related concepts

- [@Environment](/concepts/environment.md)
