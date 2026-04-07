# Week 12 Journal — Functional Programming (FP)

This week introduced Functional Programming — a paradigm that treats computation as
the evaluation of mathematical functions. Unlike OOP which organizes code around
objects and mutable state, FP focuses on transforming data through pure functions.
What stood out most is that FP is not a separate language — most modern languages
like JavaScript, Python, and Kotlin support both OOP and FP, and you use whichever
fits the problem best. *(Week 12 Lecture Notes, 2026)*

---

## The 7 Principles

**1. First-Class Functions** — Functions are values that can be stored, passed, and
returned just like any other data type.

**2. Pure Functions** — The same input always produces the same output, every time.
No surprises, no hidden behaviour.

**3. No Side Effects** — Functions do not modify anything outside their own scope.

**4. Immutability** — Values never change after creation. New values are created
instead of modifying existing ones, eliminating an entire class of bugs.

**5. Declarative Style** — Describe *what* to compute, not *how*. Code reads like
a description of the problem rather than step-by-step instructions.

**6. Function Composition** — Small, focused functions are combined into pipelines
where the output of one feeds into the next.

**7. Recursion over Loops** — Functions call themselves until a base case is reached,
replacing traditional `for` and `while` loops.

*(Reselman, B., TheServerSide, 2024)*

---

## The Three Core Tools

**map()** transforms every element in a collection and returns a new collection of
the same length. Use it to apply a function to each item.

**filter()** tests every element against a condition and keeps only those that pass.
The result is always equal to or smaller than the original.

**reduce()** collapses an entire collection into a single value using an accumulator.
It is the most powerful of the three — used for summing, flattening, or building
new structures from a collection.

The real power comes from **chaining** all three together. For example: filter
students who passed, extract their grades with map, then calculate the average with
reduce — all in one readable pipeline with no intermediate variables needed.

---

## OOP vs Functional Programming

| Aspect | OOP | Functional |
|---|---|---|
| Core unit | Class / Object | Function |
| State | Mutable | Immutable |
| Code reuse | Inheritance | Composition |
| Concurrency | Tricky | Safe |
| Loops | for / while | map / filter / reduce |

Both paradigms have their place. OOP models real-world entities well, while FP
excels at data transformation and collection processing.

---

## Reflection

What clicked for me this week is that FP is less about a specific language and more
about a way of thinking. Writing code as a series of pure transformations — rather
than instructions that mutate state — produces programs that are easier to understand,
test, and maintain. The map/filter/reduce pipeline felt immediately practical, since
it replaces verbose loop logic with something that reads almost like a sentence.

---

## References

- **Sarkar, D.P.** — Functional Programming Lecture Slides, NIC DGL 104 Winter 2026
- **Reselman, B.** — TheServerSide: [https://www.theserverside.com](https://www.theserverside.com)
- **GeeksForGeeks** — Functional Programming: [https://www.geeksforgeeks.org](https://www.geeksforgeeks.org)
- **Python Docs** — functools: [https://docs.python.org/3/library/functools.html](https://docs.python.org/3/library/functools.html)