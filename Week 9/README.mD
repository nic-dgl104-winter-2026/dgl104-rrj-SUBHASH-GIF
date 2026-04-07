# Week 9 Journal — Design Patterns

Before this week, I thought writing code was simply about solving a problem. What this
week introduced is the idea that how you solve a problem matters just as much as solving
it. Design patterns are well-proven approaches that developers have agreed on over
decades of building software. They are not rigid templates — they are flexible
structures that you adapt to your situation, much like a recipe. Learning them feels
less like learning new syntax and more like learning a shared language between
developers. *(Week 9 Lecture Notes, 2026)*

Design patterns are grouped into three families: **Creational** (how objects are
created), **Structural** (how objects are composed), and **Behavioral** (how objects
communicate). The four patterns below each fall into one of these categories.

---

## Four Key Design Patterns

### 1. Singleton *(Creational)*

Ensures only one instance of a class exists throughout the application. Useful for
things like a settings manager or database connection, where multiple instances would
cause conflicts. The pattern stores the first instance and returns it every time
instead of creating a new one. Use carefully — overuse can make code harder to test.
*(Refactoring.guru, 2014)*
```javascript
class AppConfig {
  constructor() {
    if (AppConfig.instance) return AppConfig.instance;
    this.theme = "dark";
    AppConfig.instance = this;
  }
}

const a = new AppConfig();
const b = new AppConfig();
console.log(a === b); // true
```

---

### 2. Observer *(Behavioral)*

Defines a subscription model where one object (the subject) automatically notifies
all of its dependents (observers) when its state changes. Useful for keeping UI
components in sync with data, or building event-driven systems. Always remember to
unsubscribe observers when they are no longer needed to avoid memory leaks.
*(Osmani, A., Learning JavaScript Design Patterns)*
```javascript
class Store {
  constructor() { this.observers = []; this.tasks = []; }
  subscribe(fn) { this.observers.push(fn); }
  addTask(task) {
    this.tasks.push(task);
    this.observers.forEach(fn => fn(this.tasks));
  }
}

const store = new Store();
store.subscribe(tasks => console.log("UI updated:", tasks));
store.addTask("Write journal"); // UI updated: ["Write journal"]
```

---

### 3. Factory *(Creational)*

Centralizes object creation so the rest of your code does not need to know how
objects are built — just what it needs. Especially useful when the type of object
is determined at runtime. If creation logic changes, you only update it in one place.
*(Refactoring.guru, 2014)*
```javascript
function notificationFactory(type) {
  const types = {
    email: { send: msg => console.log(`Email: ${msg}`) },
    sms:   { send: msg => console.log(`SMS: ${msg}`) }
  };
  return types[type] || null;
}

notificationFactory("sms").send("Task due tomorrow!"); // SMS: Task due tomorrow!
```

---

### 4. Strategy *(Behavioral)*

Makes behaviour swappable at runtime by wrapping each approach in its own object.
Instead of long if/else chains to handle different behaviours, you plug in whichever
strategy you need. Great for sorting, filtering, payments, or any situation where
multiple approaches to the same problem need to coexist.
*(Osmani, A., Learning JavaScript Design Patterns)*
```javascript
const sortByName = tasks => [...tasks].sort((a, b) => a.name.localeCompare(b.name));
const sortByDue  = tasks => [...tasks].sort((a, b) => new Date(a.due) - new Date(b.due));

class TaskManager {
  constructor(strategy) { this.strategy = strategy; this.tasks = []; }
  setStrategy(strategy) { this.strategy = strategy; }
  getSorted() { return this.strategy(this.tasks); }
}

const manager = new TaskManager(sortByName);
```

---

## Reflection

What stood out most this week is that design patterns are not about writing clever
code — they are about writing code that clearly communicates intent. A developer
reading a codebase that uses well-known patterns can understand the structure quickly,
even without prior familiarity with the project. That kind of clarity is what separates
maintainable software from code that becomes a burden over time.

---

## References

- **Week 9 Lecture Notes** — DGL104 Week 9 Lecture Notes *(2026)*
- **Refactoring.guru** — Design Patterns: [https://refactoring.guru/design-patterns](https://refactoring.guru/design-patterns)
- **Osmani, A.** — Learning JavaScript Design Patterns: [https://www.patterns.dev](https://www.patterns.dev)