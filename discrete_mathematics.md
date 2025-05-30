# Speaking Mathematically

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

### Set-Builder Notation

Let `S` be a set and `P(x)` a property that elements of `S` may or may not satisfy.

The set of all `x` in `S` such that `P(x)` is true is written as:

```markdown
{ x ∈ S | P(x) }
```

* Read as: *"The set of all x in S such that P(x) holds."*
* The vertical bar `|` is read as "such that".

## Axiom of Extension

A set is completely determined by **its elements**, regardless of:

* The **order** in which elements are listed
* Whether **duplicates** are listed

## Common Sets

| Symbol | Description                             |
| ------ | --------------------------------------- |
| **ℝ**  | Set of real numbers                     |
| **ℤ**  | Set of integers                         |
| **ℚ**  | Set of all rational numbers (fractions) |

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

## Definition: Relation from A to B

Let **A** and **B** be sets.  
A **relation R from A to B** is a subset of **A × B**.  
Given an ordered pair (x, y) in **A × B**,  
**x is related to y by R**, written **x R y**, if and only if **(x, y) ∈ R**.

- The set **A** is called the **domain** of **R**
- The set **B** is called the **co-domain** of **R**

**Notation:**
- `x R y` means that **(x, y) ∈ R**
- `x 𝓡̸ y` means that **(x, y) ∉ R**

## Arrow Diagram of a Relation

Suppose **R** is a relation from a set **A** to a set **B**.

The **arrow diagram** for **R** is obtained as follows:

1. Represent the elements of **A** as points in one region  
   and the elements of **B** as points in another region.

2. For each **x** in **A** and **y** in **B**,  
   draw an arrow from **x to y** if and only if **x is related to y by R**.

**Symbolically:**
- Draw an arrow from **x to y**  
  **if and only if** `x R y`  
  **if and only if** `(x, y) ∈ R`

## Definition: Function from A to B

A **function F** from a set **A** to a set **B**  
is a relation with domain **A** and co-domain **B**  
that satisfies the following two properties:

1. For every element **x** in **A**,  
   there is an element **y** in **B** such that **(x, y) ∈ F**.

2. For all elements **x** in **A** and **y** and **z** in **B**,  
   if **(x, y) ∈ F** and **(x, z) ∈ F**, then **y = z**

## Function Notation

If **A** and **B** are sets and **F** is a function from **A** to **B**,  
then given any element **x** in **A**,  
the unique element in **B** that is related to **x** by **F**  
is denoted **F(x)**, which is read **“F of x.”**

## Graph Definition

A **graph** $G$ consists of two finite sets: a nonempty set $V(G)$ of **vertices** and a set $E(G)$ of **edges**, where each edge is associated with a set consisting of either one or two vertices called its **endpoints**. The correspondence from edges to endpoints is called the **edge-endpoint function**.

An edge with just one endpoint is called a **loop**, and two or more distinct edges with the same set of endpoints are said to be **parallel**. An edge is said to **connect** its endpoints; two vertices that are connected by an edge are called **adjacent**; and a vertex that is an endpoint of a loop is said to be **adjacent to itself**.

An edge is said to be **incident on** each of its endpoints, and two edges incident on the same endpoint are called **adjacent**. A vertex on which no edges are incident is called **isolated**.

### Note

Each directed graph has an associated ordinary (undirected) graph, which is obtained by ignoring the directions of the edges.

### Directed Graph

A **directed graph**, or **digraph**, consists of two finite sets: a nonempty set $V(G)$ of vertices and a set $D(G)$ of directed edges, where each is associated with an ordered pair of vertices called its **endpoints**. If edge $e$ is associated with the pair $(v, w)$ of vertices, then $e$ is said to be the **(directed) edge** from $v$ to $w$.

### Degree of Graph

Let $G$ be a graph and $v$ a vertex of $G$. The **degree of $v$**, denoted **deg($v$)**, equals the number of edges that are incident on $v$, with an edge that is a loop counted twice.

# The Logic of Compound Statements

## Logic: Core Concepts and Definitions

### Definition of Logic

> **Logic** is the *science of the necessary laws of thought*, without which no employment of understanding or reason is possible.
> — *Immanuel Kant, 1785*

## Arguments in Logic

### What is an Argument?

* An **argument** is a sequence of statements aimed at demonstrating the truth of an assertion.
* The **conclusion** is the final statement in the sequence.
* The **premises** are the preceding statements that support the conclusion.

### Confidence in an Argument

To trust the conclusion of an argument:

* The **premises** must be:

  * Acceptable on their own merits, **or**
  * Derived from statements already known to be true.

## Form vs. Content

* Logic **analyzes the form**, not the content, of an argument.
* Logical analysis checks if:

  * The **truth of the conclusion** follows **necessarily** from the **truth of the premises**.
* Logic is often defined as:

  * The **science of necessary inference**, or
  * The **science of reasoning**.

## Definitions in Logic

### Building Definitions

* In mathematical theories, new terms are defined using **previously defined** terms.
* However, the process must **start with a few undefined terms**.

### Undefined Terms in Logic

The initial undefined terms are:

* `sentence`
* `true`
* `false`

## Statement (or Proposition)

### Definition:

> A **statement** is a sentence that is either **true or false**, but **not both**.

### Examples:

* "Two plus two equals four" → **True statement**
* "Two plus two equals five" → **False statement**

## Logic Symbols

### Basic Symbols

* `~p` means **"not p"**
* `p ∧ q` means **"p and q"**
* `p ∨ q` means **"p or q"**

### Order of Operations

* The symbol `~` is performed **first** in expressions.
* Example:

  * `~p ∧ q` = `(∼p) ∧ q`
  * `~(p ∧ q)` represents **negation** of the conjunction `p ∧ q`
* Use **parentheses** to avoid ambiguity.

  * For example, `p ∧ q ∨ r` is ambiguous.
  * Use either `(p ∧ q) ∨ r` or `p ∧ (q ∨ r)`

### Translation from English to Logic

* **"but"** is treated the same as **"and"**.

  * Example: "Jim is tall but he is not heavy" = `p ∧ q`
* **"neither-nor"** means **"not p and not q"**

  * Example: "Neither a borrower nor a lender be" = `~p ∧ ~q`

### Quick Reference Table

| English Expression | Logical Expression |
| ------------------ | ------------------ |
| `p but q`          | `p ∧ q`            |
| `neither p nor q`  | `~p ∧ ~q`          |

## Negation

> **Note:**
> Think of negation like this:
> The **negation of a statement** is a statement that exactly expresses what it would mean for the statement to be **false**.

### Definition

If `p` is a statement variable, the **negation** of `p` is:

* "**not p**"
* or
* "**It is not the case that p**"

It is denoted as: **\~p**

* If `p` is **true**, then `~p` is **false**.
* If `p` is **false**, then `~p` is **true**.

### Truth Table for Negation (\~p)

| `p` | `~p` |
| :-: | :--: |
|  T  |   F  |
|  F  |   T  |

## Conjuction

If *p* and *q* are statement variables, the **conjunction** of *p* and *q* is “*p and q*,” denoted
**p ∧ q**.

* It is **true when, and only when, both *p* and *q* are true**.
* If either *p* or *q* is false, or if both are false, **p ∧ q is false**.

### Important Note

> **Note:** The only way for an **and** statement to be true is for **both components to be true**.
> So in the truth table for an **and** statement, the **first row is the only row with a T**.

### Truth Table for **p ∧ q**

| **p** | **q** | **p ∧ q** |
| :---: | :---: | :-------: |
|   T   |   T   |     T     |
|   T   |   F   |     F     |
|   F   |   T   |     F     |
|   F   |   F   |     F     |

## **Disjunction**

###  **Two Interpretations of "Or" in Logic**

* **Exclusive Or**:

  * Means *"p or q but not both."*
  * Common in everyday speech.
  * **Example**: “Coffee, tea, or milk” — you choose one; extra payment needed for more.

* **Inclusive Or**:

  * Means *"p or q or both."*
  * Also seen in everyday speech.
  * **Example**: “Cream or sugar” — you can have both if you want.

### **Mathematical Usage**

* Mathematicians prefer the **inclusive "or"** to avoid ambiguity.
* The symbol **∨** (logical OR) comes from the Latin word ***vel***, meaning "or" in the inclusive sense.

### **Exclusive Or in Math**

* When exclusivity is needed, it's expressed as:
  **"p or q but not both."**

### **Definition Box**

> **Disjunction**:
> If *p* and *q* are statement variables, the **disjunction** of *p* and *q* is *"p or q"*, denoted as **p ∨ q**.
>
> * **True** if:
>
>   * *p* is true,
>   * *q* is true,
>   * or **both** are true.
> * **False only when both p and q are false**.

## Evaluating the Truth of More General Compound Statements

Now that truth values have been assigned to
\~p, p ∧ q, and p ∨ q, consider the question of assigning truth values to more complicated expressions such as:

* \~p ∨ q
* (p ∨ q) ∧ \~(p ∧ q)
* (p ∧ q) ∨ r

Such expressions are called **statement forms** (or **propositional forms**).

> The close relationship between statement forms and **Boolean expressions** is discussed in Section 2.4.

### Definition

**Statement form** (or **propositional form**) is:

* An expression made up of **statement variables** (such as *p*, *q*, and *r*)
* Uses **logical connectives** (such as \~, ∧, and ∨)
* Becomes a **statement** when actual statements are substituted for the variables

The **truth table** for a given statement form:

* Displays the **truth values** for all possible combinations of truth values for its component statement variables.

###  Note

Java, C, and C++ use the following notations:

| Logical Operator | Mathematical Symbol | Programming Notation |   |    |
| ---------------- | ------------------- | -------------------- | - | -- |
| NOT              | ∼                   | `!`                  |   |    |
| AND              | ∧                   | `&&`                 |   |    |
| OR               | ∨                   | \`                   |   | \` |

## *Exclusive or*
> **p ⊕ q** or **p XOR q**.

> Construct the truth table for the statement form:
> **(p ∨ q) ∧ ∼(p ∧ q)**
>
> When **or** is used in its *exclusive* sense, the statement “**p or q**” means:
> **“p or q but not both”** or **“p or q and not both p and q,”**
> which translates into symbols as:
> **(p ∨ q) ∧ ∼(p ∧ q)**.

## **Logical Equivalence**

* Two *statement forms* are called **logically equivalent** if, and only if, they have **identical truth values for each possible substitution** of statements for their statement variables.
* The logical equivalence of statement forms **P** and **Q** is denoted by writing:
  **P ≡ Q**
* Two *statements* are called **logically equivalent** if, and only if, they have **logically equivalent forms** when **identical component statement variables** are used to replace identical component statements.

### **Testing Whether Two Statement Forms P and Q Are Logically Equivalent**

1. **Construct a truth table**:

   * Include one column for the truth values of **P**.
   * Include another column for the truth values of **Q**.

2. **Compare the truth values of P and Q** for each row:

   * **(a)** If in **each row**, the truth value of **P** is the **same** as **Q**, then **P and Q are logically equivalent**.
   * **(b)** If in **any row**, the truth value of **P** is **different** from **Q**, then **P and Q are not logically equivalent**.

## **Tautology and Contradiction**

1. **Tautology**

   * A **tautology** is a statement form that is **always true**, regardless of the truth values of its component statements.
   * A statement with the form of a tautology is called a **tautological statement**.

2. **Contradiction**

   * A **contradiction** is a statement form that is **always false**, regardless of the truth values of its component statements.
   * A statement with the form of a contradiction is called a **contradictory statement**.

3. **Structure Over Meaning**

   * The **truth of tautological statements** and the **falsity of contradictory statements** comes from their **logical structure**, not the meanings of the actual statements.

##    Theorem 2.1.1 — Logical Equivalences (Tabular Format)

| **#** | **Law**                  | **Equivalence(s)**                                                                                                    |
| ----: | ------------------------ | --------------------------------------------------------------------------------------------------------------------- |
|     1 | **Commutative**          | $p \land q \equiv q \land p$ <br> $p \lor q \equiv q \lor p$                                                          |
|     2 | **Associative**          | $(p \land q) \land r \equiv p \land (q \land r)$ <br> $(p \lor q) \lor r \equiv p \lor (q \lor r)$                    |
|     3 | **Distributive**         | $p \land (q \lor r) \equiv (p \land q) \lor (p \land r)$ <br> $p \lor (q \land r) \equiv (p \lor q) \land (p \lor r)$ |
|     4 | **Identity**             | $p \land t \equiv p$ <br> $p \lor c \equiv p$                                                                         |
|     5 | **Negation**             | $p \lor \sim p \equiv t$ <br> $p \land \sim p \equiv c$                                                               |
|     6 | **Double Negative**      | $\sim(\sim p) \equiv p$                                                                                               |
|     7 | **Idempotent**           | $p \land p \equiv p$ <br> $p \lor p \equiv p$                                                                         |
|     8 | **Universal Bound**      | $p \lor t \equiv t$ <br> $p \land c \equiv c$                                                                         |
|     9 | **De Morgan’s**          | $\sim(p \land q) \equiv \sim p \lor \sim q$ <br> $\sim(p \lor q) \equiv \sim p \land \sim q$                          |
|    10 | **Absorption**           | $p \lor (p \land q) \equiv p$ <br> $p \land (p \lor q) \equiv p$                                                      |
|    11 | **Negations of t and c** | $\sim t \equiv c$ <br> $\sim c \equiv t$                                                                              |

## Conditional Statements

> *“...hypothetical reasoning implies the subordination of the real to the realm of the possible...”*
> — *Jean Piaget, 1972*

### Key Concepts

* **Logical Inference**:

  * Reasoning **from a hypothesis to a conclusion**.
  * Objective: To say, *“If such and such is known, then something else must be true.”*

* **Form of a Conditional Statement**:

  * Let **p** and **q** be statements.
  * A conditional statement is written as:
    **"If p, then q"**
    or symbolically: **p → q**
  * **p** = *hypothesis*
  * **q** = *conclusion*

### Example:

> **If 4,686 is divisible by 6, then 4,686 is divisible by 3**

* **Hypothesis**: 4,686 is divisible by 6
* **Conclusion**: 4,686 is divisible by 3

### Terminology

* A sentence like this is called a **conditional statement**.
* The **truth of q** is **conditioned on the truth of p**.

### Example Scenario:

**Promise:**

> "If you show up for work Monday morning, then you will get the job."

**Question:**
When can you say this promise is false?

**Answer:**
Only if:

* You **do** show up for work Monday morning (**p = true**)
* But you **do not** get the job (**q = false**)

### Key Insight:

> A conditional sentence is **only false when the hypothesis is true and the conclusion is false**.

So, for a conditional **p → q**:

* **True** when:

  * p = T, q = T ✅
  * p = F, q = T ✅
  * p = F, q = F ✅
* **False** only when:

  * p = T, q = F ❌

### Truth Table for $p \rightarrow q$

| p | q | $p \rightarrow q$ |
| - | - | ----------------- |
| T | T | T                 |
| T | F | F                 |
| F | T | T                 |
| F | F | T                 |

### Definition:

If **p** and **q** are statement variables:

* The **conditional** of q by p is:

  > "If p then q" or "p implies q", denoted **$p \rightarrow q$**.
* It is **false** only when:

  * **p = true** and **q = false**
* In all other cases, it is **true**.

**Terminology:**

* **p**: Hypothesis (or Antecedent)
* **q**: Conclusion (or Consequent)

## Vacuously True Statements

### What Is a Vacuously True Statement?

A **conditional statement** is said to be **vacuously true** (or **true by default**) when:

* The **hypothesis (the “if” part)** is **false**,
* Regardless of whether the **conclusion** is true or false.

### Example:

> **“If you show up for work Monday morning, then you will get the job.”**

* If you **do not** show up Monday morning (i.e., **hypothesis is false**),
  then the entire statement is **vacuously true** — even if you don’t get the job.

### General Rule:

> In an **if-then** statement, when the **“if” part is false**,
> the entire statement is considered **true**,
> **no matter what** the conclusion is.

### Summary:

| Hypothesis (p) | Conclusion (q) | Statement $p \rightarrow q$ | Explanation    |
| -------------- | -------------- | --------------------------- | -------------- |
| False          | True           | True                        | Vacuously true |
| False          | False          | True                        | Vacuously true |

## 📘 Representation of If-Then as Or

* You are asked to use truth tables to show that:

  $p \rightarrow q \equiv \sim p \lor q$

* The logical equivalence of “if *p* then *q*” and “not *p* or *q*” is used in everyday speech.

## 🔹 Example 2.2.4

### **Application of the Equivalence between**  $\sim p \lor q$ **and** $p \rightarrow q$

**Problem:**
Rewrite the following statement in if-then form:

> *Either you get to work on time or you are fired.*

**Solution:**

* Let $\sim p$: *You get to work on time*
  → So, $p$: *You do not get to work on time*

* Let $q$: *You are fired*

* The given statement:
  $\sim p \lor q$

* Equivalent if-then form:
  $p \rightarrow q$

> **If you do not get to work on time, then you are fired.**

