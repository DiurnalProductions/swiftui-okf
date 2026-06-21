# SwiftUI Knowledge Pack

> SwiftUI is a **declarative framework where views are functions of state**. You describe what the interface should look like for the current state; SwiftUI reconciles that description with what is on screen.

This OKF knowledge pack covers modern SwiftUI on iOS 18+, macOS, watchOS, and visionOS. It assumes a separate [Swift knowledge pack](../) exists for language fundamentals.

## Start Here

If you are new to SwiftUI, begin with the declarative model before touching state or layout:

1. [Views as Functions of State](/concepts/views.md) — the core mental model
2. [Body Recomputation](/concepts/body_recomputation.md) — why SwiftUI re-evaluates your UI constantly
3. [Data Flow](/concepts/data_flow.md) — state flows down, actions flow up
4. [Source of Truth](/concepts/source_of_truth.md) — who owns each piece of state

---

## Declarative UI Model

* [Views as Functions of State](/concepts/views.md) — views are ephemeral value-type descriptions, not persistent widgets
* [Body Recomputation](/concepts/body_recomputation.md) — `body` is re-evaluated whenever dependencies change
* [View Identity](/concepts/identity.md) — how SwiftUI tracks which view is which across updates
* [Diffing and Reconciliation](/concepts/diffing.md) — how SwiftUI updates the render tree efficiently

**Recommended order:** views → body recomputation → identity → diffing

---

## State Management

* [Source of Truth](/concepts/source_of_truth.md) — single owner for each piece of mutable state
* [Data Flow](/concepts/data_flow.md) — unidirectional flow from parent to child
* [@State](/concepts/state.md) — local private state owned by a view
* [@Binding](/concepts/binding.md) — two-way reference to a parent's state
* [@Observable](/concepts/observable.md) — reference-type models that trigger view updates
* [@Environment](/concepts/environment.md) — read values propagated through the view tree
* [@EnvironmentObject](/concepts/environment_object.md) — inject shared observable models

**Recommended order:** source of truth → data flow → @State → @Binding → @Observable → @Environment → @EnvironmentObject

---

## View Composition

* [Composition Over Inheritance](/concepts/composition.md) — build complex UI from small reusable pieces
* [Containers](/concepts/containers.md) — stack and group views into structured layouts
* [Reusable Views](/concepts/reusable_views.md) — extract parameterized subviews
* [Modifiers](/concepts/modifiers.md) — transform views by returning new view values

---

## Layout

* [VStack](/concepts/vstack.md) — vertical stacking
* [HStack](/concepts/hstack.md) — horizontal stacking
* [ZStack](/concepts/zstack.md) — depth-based layering
* [Spacer](/concepts/spacer.md) — flexible empty space
* [Alignment](/concepts/alignment.md) — positioning within stacks and frames
* [Frame Behavior](/concepts/frame.md) — sizing proposals and constraints
* [GeometryReader](/concepts/geometry_reader.md) — read available space from a parent
* [Custom Layouts](/concepts/custom_layouts.md) — Layout protocol for bespoke arrangement

**Recommended order:** containers → alignment → VStack/HStack/ZStack → Spacer → frame → GeometryReader → custom layouts

---

## Navigation

* [NavigationStack](/concepts/navigation_stack.md) — path-based stack navigation
* [Navigation Destinations](/concepts/navigation_destinations.md) — type-safe push destinations
* [Tab Views](/concepts/tab_views.md) — top-level section switching
* [Sheet Presentation](/concepts/sheet_presentation.md) — slide-up modal sheets
* [Modal Presentation](/concepts/modal_presentation.md) — full-screen and custom presentations

**Recommended order:** NavigationStack → navigation destinations → tab views → sheets → modal presentation

---

## Lists and Collections

* [ForEach](/concepts/foreach.md) — iterate data into views with identity
* [List](/concepts/list.md) — platform-native scrollable rows
* [LazyVStack](/concepts/lazy_vstack.md) — vertically lazy-loaded stacks
* [LazyHStack](/concepts/lazy_hstack.md) — horizontally lazy-loaded stacks
* [Grids](/concepts/grids.md) — LazyVGrid and LazyHGrid for grid layouts

**Recommended order:** ForEach → List → lazy stacks → grids

---

## Animation

* [Implicit Animations](/concepts/implicit_animations.md) — animate state-driven changes automatically
* [Explicit Animations](/concepts/explicit_animations.md) — control animation with `withAnimation`
* [Transitions](/concepts/transitions.md) — animate view insertion and removal
* [Matched Geometry Effect](/concepts/matched_geometry_effect.md) — shared-element transitions between views

**Recommended order:** implicit → explicit → transitions → matched geometry effect

---

## Async UI Behavior

* [MainActor](/concepts/main_actor.md) — UI updates must happen on the main thread
* [Async Data Loading](/concepts/async_data_loading.md) — fetch data off the main thread, publish on MainActor
* [.task Modifier](/concepts/task_modifier.md) — structured async work tied to view lifetime
* [Cancellation](/concepts/cancellation.md) — cancel async work when views disappear

**Recommended order:** MainActor → async data loading → .task → cancellation

---

## Architecture

* [State Ownership](/concepts/state_ownership.md) — decide where state lives in the tree
* [Separation of Concerns](/concepts/separation_of_concerns.md) — keep views thin, models focused
* [MVVM in SwiftUI](/concepts/mvvm.md) — model–view–viewmodel pattern adapted for declarative UI
* [Dependency Injection](/concepts/dependency_injection.md) — pass dependencies via initializer or environment

**Recommended order:** state ownership → separation of concerns → MVVM → dependency injection

---

## Persistence

* [AppStorage](/concepts/app_storage.md) — UserDefaults-backed persistent state
* [SceneStorage](/concepts/scene_storage.md) — restore transient UI state across scene sessions
* [SwiftData Concepts](/concepts/swiftdata_concepts.md) — high-level persistence with @Model and @Query

---

## Environment

* [Environment Values](/concepts/environment_values.md) — typed key–value propagation through the tree
* [Dependency Propagation](/concepts/dependency_propagation.md) — implicit injection without explicit parameters
* [Themes and Appearance](/concepts/themes_appearance.md) — color scheme, typography, and styling via environment

**Recommended order:** environment values → dependency propagation → themes and appearance

---

## Full Recommended Learning Path

1. **Foundation:** views → body recomputation → identity → diffing
2. **State:** source of truth → data flow → @State → @Binding
3. **Composition:** composition → containers → modifiers → reusable views
4. **Layout:** alignment → VStack → HStack → ZStack → Spacer → frame
5. **Collections:** ForEach → List → lazy stacks → grids
6. **Shared state:** @Observable → @Environment → @EnvironmentObject
7. **Navigation:** NavigationStack → destinations → tabs → sheets
8. **Animation:** implicit → explicit → transitions
9. **Async:** MainActor → async data loading → .task → cancellation
10. **Architecture:** state ownership → MVVM → dependency injection
11. **Persistence & environment:** AppStorage → SwiftData concepts → environment values
