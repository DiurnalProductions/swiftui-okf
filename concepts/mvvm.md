---
id: swiftui.mvvm
type: concept
title: MVVM in SwiftUI
description: Model-View-ViewModel pattern adapted for declarative UI with observable view models.
tags: [swiftui, architecture, mvvm]
prerequisites:
  - swiftui.observable
  - swiftui.state_ownership
  - swiftui.separation_of_concerns
related:
  - swiftui.dependency_injection
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

In SwiftUI MVVM, the **View** is declarative, the **Model** is domain data, and the **ViewModel** (`@Observable` class) exposes UI state and actions.

## Mental model

ViewModel is the **adapter** between domain and UI. Views observe view models; view models don't know about specific views.

## Example

```swift
@Observable
class LoginViewModel {
    var email = ""
    var isLoading = false
    func login() async { /* ... */ }
}

struct LoginView: View {
    @State private var vm = LoginViewModel()
    var body: some View { /* bind to vm */ }
}
```

## Common mistakes

- ViewModels that reference View types.
- Creating ViewModels in `body` instead of `@State` or injection.

## Related concepts

- [State Ownership](/concepts/state_ownership.md)
