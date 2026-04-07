# Week 10 Journal — MV* Architectural Patterns

This week introduced MV* patterns, which define the overall structure of an
application. Unlike design patterns that solve specific coding problems, MV* patterns
are architectural — they shape how an entire project is organized. The core idea
shared across all MV* patterns is separating the **data** (Model) from the
**interface** (View), with a middle layer managing the relationship between the two.
Without this separation, data logic and UI logic tend to get tangled together, making
code difficult to maintain as an application grows. *(Week 10 Lecture Notes, 2026)*

---

## The Three Patterns

### 1. MVC — Model View Controller

The **Controller** acts as the middle layer. It receives user input, updates the
**Model**, and decides which **View** to display. The Model and View never
communicate directly — everything goes through the Controller.
User Input → Controller → Model → View → User sees result

MVC is best suited for server-side web applications. Frameworks like Ruby on Rails
are built around this pattern.

---

### 2. MVVM — Model View ViewModel

The **ViewModel** exposes data from the Model, and the **View** binds to it directly.
When the ViewModel's data changes, the View updates automatically — no manual
intervention needed.
Model ↔ ViewModel ↔ (data binding) ↔ View

MVVM is the preferred pattern for modern declarative UI frameworks like SwiftUI
(iOS) and Jetpack Compose (Android). It also makes logic easier to test since the
ViewModel can be tested independently of the UI.

---

### 3. MVP — Model View Presenter

The **Presenter** handles all logic and updates the **View** directly through an
interface. The View is completely passive — it only displays what the Presenter
tells it to and forwards user actions back.
View ↔ Presenter ↔ Model

MVP enforces a stricter separation than MVC, making the View easy to swap out
without touching any logic.

## Reflection

What stood out most this week is that architecture matters as much as code quality.
MV* patterns give teams a shared structure to work within, making codebases easier
to navigate and maintain. Understanding the distinction between MVC, MVVM, and MVP
also helps when choosing the right framework for a project, since each pattern is
closely tied to specific tools and platforms.

---

## References

- **Week 10 Lecture Notes** — DGL104 Week 10 Lecture Notes *(2026)*
- **Osmani, A.** — Learning JavaScript Design Patterns:
  [https://www.patterns.dev](https://www.patterns.dev)
- **Refactoring.guru** — Design Patterns:
  [https://refactoring.guru/design-patterns](https://refactoring.guru/design-patterns)