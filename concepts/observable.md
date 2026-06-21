---
id: swiftui.observable
type: concept
title: @Observable
description: The Observation framework macro that makes reference-type models automatically invalidate dependent views.
tags: [swiftui, state, observation]
prerequisites:
  - swiftui.source_of_truth
  - swift.structures
related:
  - swiftui.environment_object
  - swiftui.mvvm
  - swiftui.swiftdata_concepts
resource: https://developer.apple.com/documentation/swiftui
timestamp: 2026-06-20
---

## Summary

`@Observable` marks a class whose property changes trigger view updates. Views read properties directly; SwiftUI tracks access and re-evaluates when they change.

## Mental model

An `@Observable` class is a **reference-type model** outside the view struct. Create it once at an appropriate owner — never in `body`.

## Example

```swift
@Observable
class CounterModel { var count = 0 }

struct CounterView: View {
    var model: CounterModel
    var body: some View {
        Button("Count: \(model.count)") { model.count += 1 }
    }
}
```

## Common mistakes

- Instantiating `@Observable` objects inside `body`.
- Expecting untracked property changes to update views.
- Mutating from background threads without `@MainActor`.

## Related concepts

- [MVVM in SwiftUI](/concepts/mvvm.md)
- [@EnvironmentObject](/concepts/environment_object.md)
