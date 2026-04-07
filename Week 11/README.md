# Week 11 Journal — Object-Oriented Programming (OOP)

This week introduced Object-Oriented Programming — a way of organizing code around
data and real-world entities rather than a sequence of instructions. Before OOP,
procedural programming dominated, where data flowed freely between functions and was
often stored globally. This made large programs difficult to maintain because any
function could accidentally modify shared data. OOP was developed to fix this by
grouping data and behaviour together into protected, self-contained units.
*(Week 11 Lecture Notes, 2026)*

---

## Core Concepts

### Classes and Objects

A **class** is a blueprint that defines what something should look like and how it
should behave. An **object** is a specific instance of that class — the actual,
usable version in memory. Think of a class as a house blueprint and objects as the
houses built from it. You can create many different objects from the same class,
each with their own unique data.

---

### Encapsulation

Encapsulation bundles data and the functions that work with it into one unit, and
restricts direct access from outside. This protects data from accidental changes —
a concept known as **data hiding**. A good real-world analogy is an ATM: you
interact with the interface, but the internal banking logic is completely hidden
from you.

---

### Inheritance

Inheritance lets a new class take on the properties and behaviours of an existing
class and extend them. This promotes code reuse — instead of rewriting common logic,
you inherit it and only define what is new or different. For example, a `Student`
is a type of `Person`. Rather than redefining shared properties like name and age,
a Student class can inherit them from Person and only add student-specific details.

---

### Polymorphism

Polymorphism means the same method name can behave differently depending on which
object calls it. Each child class can override a parent method with its own specific
behaviour, and the correct version is selected automatically at runtime through
**dynamic binding**. A practical example is a `draw()` method on a Shape class —
a Circle, Rectangle, and Triangle would each draw differently, but all share the
same method name.

---

### Abstraction and Message Passing

**Abstraction** means exposing only what is necessary and hiding the complexity
underneath — like driving a car without needing to understand how the engine works.
**Message passing** is how objects communicate with each other by calling each
other's methods. This keeps objects loosely coupled — each only needs to know what
to ask another object, not how that object handles the request internally.

---

## Reflection

OOP makes sense because it mirrors how we naturally think — in terms of things, not
procedures. Modelling a student, a bank account, or a vehicle as an object feels
intuitive. More importantly, OOP produces code that is easier to maintain, extend,
and scale as a project grows. Understanding these core concepts — classes, objects,
encapsulation, inheritance, and polymorphism — is foundational to working with most
modern programming languages and frameworks.

---

## References

- **Week 11 Lecture Notes** — DGL104 Week 11 Lecture Notes *(2026)*
- **Sarkar, D.P.** — OOP Lecture Notes, NIC DGL 104 Winter 2026
- **MDN Web Docs** — JavaScript Classes:
  [https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes)