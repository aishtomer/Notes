## Universal Statement

A **universal statement** asserts that a certain property holds for **all elements** in a set.

> **Example:**
> *All positive numbers are greater than zero.*

## Conditional Statement

A **conditional statement** asserts that if one thing is true, then **another thing must also be true**.

> **Example:**
> *If 378 is divisible by 18, then 378 is divisible by 6.*

## Existential Statement

An **existential statement** claims that there is **at least one element** for which a property holds.

> **Example:**
> *There is a prime number that is even.*

## Additive Inverse

For a number `b` to be an **additive inverse** of a number `a`, it must satisfy:

```
a + b = 0
```

---

## Set Notation

### Set-Roster Notation

If `S` is a set:

* `x ∈ S`: *x is an element of S*
* `x ∉ S`: *x is not an element of S*

A set can be defined by listing its elements:

```markdown
{1, 2, 3}
```

For large or infinite sets, we use ellipsis `...`:

* `{1, 2, 3, ..., 100}`: all integers from 1 to 100
* `{1, 2, 3, ...}`: all positive integers

---

### Set-Builder Notation

Let `S` be a set and `P(x)` a property that elements of `S` may or may not satisfy.

The set of all `x` in `S` such that `P(x)` is true is written as:

```markdown
{ x ∈ S | P(x) }
```

* Read as: *"The set of all x in S such that P(x) holds."*
* The vertical bar `|` is read as "such that".

---

## Axiom of Extension

A set is completely determined by **its elements**, regardless of:

* The **order** in which elements are listed
* Whether **duplicates** are listed

---

## Common Sets

| Symbol | Description                             |
| ------ | --------------------------------------- |
| **ℝ**  | Set of real numbers                     |
| **ℤ**  | Set of integers                         |
| **ℚ**  | Set of all rational numbers (fractions) |

---

## Subsets

### Subset

If `A` and `B` are sets:

```markdown
A ⊆ B
```

Means: *Every element of A is also an element of B.*

> **Symbolically:**
> ∀x (x ∈ A → x ∈ B)

### Not a Subset

```markdown
A ⊈ B
```

Means: *There is at least one element of A that is not in B.*

> **Symbolically:**
> ∃x (x ∈ A ∧ x ∉ B)

### Proper Subset

`A` is a **proper subset** of `B` if:

* Every element of `A` is in `B`, **and**
* There is at least one element in `B` **not** in `A`

---

## Ordered Pairs and Tuples

### Ordered Pair

An **ordered pair** `(a, b)` consists of:

* First element: `a`
* Second element: `b`

```markdown
(a, b) = (c, d) ⇔ a = c and b = d
```

### Ordered n-Tuple

For a positive integer `n`, and elements `x₁, x₂, ..., xₙ`, the **ordered n-tuple** is:

```markdown
(x₁, x₂, ..., xₙ)
```

Equality condition:

```markdown
(x₁, ..., xₙ) = (y₁, ..., yₙ) ⇔ x₁ = y₁, ..., xₙ = yₙ
```

---

## Cartesian Product

Given sets `A₁, A₂, ..., Aₙ`, their **Cartesian product** is:

```markdown
A₁ × A₂ × ⋯ × Aₙ = { (a₁, a₂, ..., aₙ) | a₁ ∈ A₁, a₂ ∈ A₂, ..., aₙ ∈ Aₙ }
```

### Cartesian Product of Two Sets

```markdown
A₁ × A₂ = { (a₁, a₂) | a₁ ∈ A₁ and a₂ ∈ A₂ }
```

---

## Strings over a Set

Let `A` be a finite set and `n` a positive integer.

* A **string of length `n` over `A`** is an ordered `n`-tuple of elements of `A`, written **without parentheses or commas**.
* **Characters** of the string are the elements of `A`.

### Null String

* The **null string** (empty string) over `A` is denoted by `λ`
* It has **length 0**

### Bit Strings

If `A = {0, 1}`, then strings over `A` are called **bit strings**.

---
