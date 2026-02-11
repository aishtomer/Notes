# Sparse Table

This is a comprehensive, deep dive into the **Sparse Table** data structure.

To understand Sparse Tables, we cannot simply look at the code. We must understand the specific problem it solves, the mathematical property it exploits, and why it is often preferred over more complex structures like Segment Trees for specific tasks.

---

## Part 1: The Prerequisites

Before building the table, we need to establish the foundational concepts.

### 1. The Problem: Static Range Minimum Query (RMQ)
Imagine you have an array of numbers that **does not change** (it is static). You are bombarded with thousands of questions asking: *"What is the minimum value between index $L$ and index $R$?"*

**Array:** `[1, 5, -2, 4, 8, 7]`
*   Query(0, 2) $\to$ Min of `[1, 5, -2]` is **-2**.
*   Query(3, 5) $\to$ Min of `[4, 8, 7]` is **4**.

#### Why not use simple approaches?
1.  **Naive Loop:** For every query, loop from $L$ to $R$.
    *   Time Complexity: $O(N)$ per query. Too slow if we have $10^5$ queries.
2.  **Precomputed 2D Matrix:** Store the answer for *every possible* pair $(L, R)$.
    *   Time Complexity: $O(1)$ per query.
    *   Space Complexity: $O(N^2)$. If $N = 10^5$, $N^2 = 10^{10}$ (10 billion integers), which will crash your memory.

**The Sparse Table Goal:**
We want $O(1)$ query time (instant answers) but with a manageable space complexity of $O(N \log N)$.

### 2. Prerequisite Concept: Idempotency
This is the most critical mathematical property for Sparse Tables.
An operation is **Idempotent** if applying it multiple times to the same input produces the same result.

*   **Addition is NOT Idempotent:** $5 + 5 \neq 5$.
*   **Minimum IS Idempotent:** $\min(5, 5) = 5$.
*   **Maximum IS Idempotent:** $\max(5, 5) = 5$.
*   **GCD IS Idempotent:** $\text{gcd}(5, 5) = 5$.

**Why does this matter?**
If we want to sum range $[0, 5]$, we must be careful not to count any number twice. `Sum([0,3]) + Sum([2,5])` would count indices 2 and 3 twice, giving the wrong answer.

However, for Minimum:
$$\min(\text{Range}[0, 3], \text{Range}[2, 5])$$
Even though indices 2 and 3 are included in *both* ranges, the result is still correct because $\min(x, x) = x$.

**Conclusion:** Sparse Tables allow us to use **overlapping ranges** to answer queries, provided the operation is idempotent (Min, Max, GCD, OR, AND).

### 3. Prerequisite Concept: Powers of Two
Sparse Tables rely entirely on powers of two ($1, 2, 4, 8, 16, \dots$).
Any positive integer can be represented as a sum of powers of two (Binary representation), but for Sparse Tables, we specifically care about the fact that:
**Any interval of length $L$ can be covered by two overlapping intervals of length $2^k$, where $2^k$ is the largest power of 2 less than or equal to $L$.**

---

## Part 2: The Core Concept - What is a Sparse Table?

A Sparse Table is a 2D array, let's call it `st`.
`st[i][j]` does **not** store a simple coordinate.

#### The Definition
`st[i][j]` stores the answer (e.g., Minimum) for the range starting at index **$i$** with length **$2^j$**.

*   **$i$**: The starting index of the range.
*   **$j$**: The exponent of the power of 2 (The length is $2^j$).

**Visualizing the Dimensions:**
*   `st[i][0]` covers range $[i, i + 2^0 - 1]$ $\to$ Length 1 (Just the element itself).
*   `st[i][1]` covers range $[i, i + 2^1 - 1]$ $\to$ Length 2.
*   `st[i][2]` covers range $[i, i + 2^2 - 1]$ $\to$ Length 4.
*   `st[i][3]` covers range $[i, i + 2^3 - 1]$ $\to$ Length 8.

Because the maximum length is $N$, the power $j$ only needs to go up to $\lfloor \log_2 N \rfloor$. This gives us the $O(N \log N)$ size.

---

## Part 3: Building the Table (The Preprocessing)

We build the table using **Dynamic Programming**.

#### 1. Base Case ($j=0$)
Ranges of length $2^0 = 1$ are just the array elements themselves.
`st[i][0] = array[i]`

#### 2. The Recursive Step
How do we find the minimum of a range of length $2^j$?
We split it into **two halves** of length $2^{j-1}$.

Imagine we want to calculate `st[i][j]` (Range of length 8).
We can combine:
1.  `st[i][j-1]` (First 4 elements).
2.  `st[i + 2^(j-1)][j-1]` (Next 4 elements).

**The Formula:**
$$ st[i][j] = \min(st[i][j-1], \quad st[i + 2^{j-1}][j-1]) $$

#### Python Implementation: The Builder

```python
import math

def build_sparse_table(arr):
    n = len(arr)
    # The max power of 2 needed. 
    # Example: if n=10, log2(10) is ~3.32, so K=3. 2^3=8.
    K = int(math.log2(n)) + 1
    
    # Initialize table with 0s. Dimensions: [N][K]
    st = [[0] * K for _ in range(n)]

    # STEP 1: Base Case (Length 1)
    for i in range(n):
        st[i][0] = arr[i]

    # STEP 2: Fill the table for lengths 2, 4, 8...
    # j represents the power of 2. We loop from 1 to K.
    for j in range(1, K):
        # i represents the starting index.
        # We stop when i + 2^j > n because that range would go out of bounds.
        range_len = 1 << j       # 2^j
        half_len = 1 << (j - 1)  # 2^(j-1)
        
        for i in range(n - range_len + 1):
            # The Logic: Min of First Half vs Min of Second Half
            st[i][j] = min(st[i][j-1], st[i + half_len][j-1])
            
    return st

# Example usage:
data = [1, 5, -2, 4, 8, 7]
table = build_sparse_table(data)

# Let's inspect st[2][1]
# Starts at index 2, Length 2^1 = 2. Range: [-2, 4]. Min should be -2.
print(f"Min of range starting at 2 with len 2: {table[2][1]}") 
```

**Time Complexity Analysis:**
*   Outer loop runs $\log N$ times.
*   Inner loop runs $N$ times.
*   Total: **$O(N \log N)$**.

---

## Part 4: Querying the Table

This is where the magic of overlapping intervals happens.

Suppose we want the Minimum of range $[L, R]$.
The length of this range is $\text{len} = R - L + 1$.

In most cases, $\text{len}$ is **not** a perfect power of 2. So we cannot just look up `st[L][something]`.

**The Strategy:**
1.  Find the largest power of 2, let's call it $2^k$, that fits inside our range.
    $$ k = \lfloor \log_2(R - L + 1) \rfloor $$
2.  Look at the interval starting at $L$ with length $2^k$: `st[L][k]`.
3.  Look at the interval **ending at $R$** with length $2^k$.
    *   This interval starts at index: $R - 2^k + 1$.
    *   Lookup: `st[R - 2^k + 1][k]`.

**Wait, do they overlap?**
Yes! Unless the range length is exactly $2^k$, these two intervals will overlap in the middle.
Because Min is **idempotent**, the overlap doesn't corrupt the data.

**The Query Formula:**
$$ \text{Query}(L, R) = \min(st[L][k], \quad st[R - 2^k + 1][k]) $$

#### Example Trace
Array: `[1, 5, -2, 4, 8, 7]`
Query: $L=1, R=5$ (Range: `[5, -2, 4, 8, 7]`). Correct Min: -2.
Length: $5 - 1 + 1 = 5$.

1.  Calculate $k$: $\lfloor \log_2(5) \rfloor = 2$. Max power of 2 is $2^2 = 4$.
2.  **Left Interval:** Starts at 1, length 4.
    *   Indices: `[1, 2, 3, 4]` (Values: `5, -2, 4, 8`)
    *   Lookup `st[1][2]`. Result: -2.
3.  **Right Interval:** Ends at 5, length 4.
    *   Start index: $5 - 4 + 1 = 2$.
    *   Indices: `[2, 3, 4, 5]` (Values: `-2, 4, 8, 7`)
    *   Lookup `st[2][2]`. Result: -2.
4.  **Result:** $\min(-2, -2) = -2$.

Notice that indices 2, 3, and 4 were checked in *both* lookups. This is perfectly fine.

#### Python Implementation: The Query

```python
def query_sparse_table(st, L, R):
    # Calculate length
    length = R - L + 1
    
    # Calculate k (largest power of 2 that fits)
    k = int(math.log2(length))
    
    # Left interval min
    left_min = st[L][k]
    
    # Right interval min
    # 1 << k means 2^k
    right_min = st[R - (1 << k) + 1][k]
    
    return min(left_min, right_min)
```

**Time Complexity Analysis:**
*   `math.log2`: Assumed to be $O(1)$ (or very close to it with hardware support).
*   Array lookup: $O(1)$.
*   Min operation: $O(1)$.
*   Total: **$O(1)$**.

---

## Part 5: The Complete Optimized Class

To make this production-ready (for competitive programming like LeetCode or Codeforces), we need to optimize the `log` calculation. Calling `math.log2` repeatedly can be slightly slow. We can precompute logarithms for all numbers up to $N$.

Here is the complete, detailed Python Class.

```python
import math

class SparseTable:
    def __init__(self, arr, func=min):
        """
        Initialize Sparse Table.
        :param arr: The input array.
        :param func: The idempotent function (min, max, gcd). Default is min.
        """
        self.n = len(arr)
        self.func = func
        
        # Precompute logs for O(1) retrieval
        # log_table[i] will store floor(log2(i))
        self.log_table = [0] * (self.n + 1)
        for i in range(2, self.n + 1):
            self.log_table[i] = self.log_table[i // 2] + 1
            
        # K is the maximum power of 2 needed
        self.K = self.log_table[self.n]
        
        # Initialize the table with dimension [N][K + 1]
        # self.st[i][j] stores func of range starting at i with length 2^j
        self.st = [[0] * (self.K + 1) for _ in range(self.n)]
        
        self._build(arr)

    def _build(self, arr):
        # Base case: Intervals of length 1 (2^0)
        for i in range(self.n):
            self.st[i][0] = arr[i]

        # Build remaining layers
        # j ranges from 1 to K
        for j in range(1, self.K + 1):
            range_len = 1 << j       # 2^j
            half_len = 1 << (j - 1)  # 2^(j-1)
            
            # We iterate until the interval goes out of bounds
            for i in range(self.n - range_len + 1):
                val1 = self.st[i][j-1]
                val2 = self.st[i + half_len][j-1]
                self.st[i][j] = self.func(val1, val2)

    def query(self, L, R):
        """
        Query the range [L, R] inclusive (0-indexed).
        """
        if L > R:
            return float('inf') # Or handle error
            
        # Get precomputed log value
        length = R - L + 1
        k = self.log_table[length]
        
        # Overlapping intervals logic
        left_interval = self.st[L][k]
        right_interval = self.st[R - (1 << k) + 1][k]
        
        return self.func(left_interval, right_interval)

# --- DRIVER CODE AND EXAMPLES ---

# 1. Standard Minimum Query
data = [1, 5, -2, 4, 8, 7, 6, 0]
rmq = SparseTable(data, min)

print(f"Array: {data}")
print(f"Min [1, 4] (5, -2, 4, 8): {rmq.query(1, 4)}") # Expect -2
print(f"Min [4, 7] (8, 7, 6, 0): {rmq.query(4, 7)}") # Expect 0

# 2. Maximum Query (Sparse Tables work for Max too!)
rmq_max = SparseTable(data, max)
print(f"Max [1, 4] (5, -2, 4, 8): {rmq_max.query(1, 4)}") # Expect 8

# 3. GCD Query (Greatest Common Divisor is idempotent)
# gcd(a, b, c) = gcd(gcd(a,b), c)
import math
data_gcd = [24, 12, 36, 48, 16]
rmq_gcd = SparseTable(data_gcd, math.gcd)
print(f"GCD [0, 2] (24, 12, 36): {rmq_gcd.query(0, 2)}") # Expect 12
print(f"GCD [0, 4] (All): {rmq_gcd.query(0, 4)}")       # Expect 4
```

---

## Part 6: Comparison - Why/When to use Sparse Table?

You might ask: "Segment Trees can also do Range Minimum Query. Why learn Sparse Table?"

| Feature | Sparse Table | Segment Tree |
| :--- | :--- | :--- |
| **Build Time** | $O(N \log N)$ | $O(N)$ |
| **Query Time** | **$O(1)$** | $O(\log N)$ |
| **Space** | $O(N \log N)$ | $O(N)$ |
| **Updates?** | **Impossible (Static only)** | Very Fast ($O(\log N)$) |
| **Operations** | Idempotent only (Min, Max, GCD) | Any Associative (Sum, Min, Max, XOR) |

#### Summary of Use Cases:
1.  **Use Sparse Table if:**
    *   The array is **Static** (values never change after building).
    *   You have huge number of queries (e.g., $10^6$ queries on $10^5$ elements). The $O(1)$ speed difference vs $O(\log N)$ adds up.
    *   The operation is Min, Max, GCD, OR, or AND.

2.  **Use Segment Tree if:**
    *   The array values change (Point updates or Range updates).
    *   You need to calculate **Sum** (Sum is not idempotent, so the overlapping trick fails).

#### Why does Sum fail with Sparse Table?
If you try to Query Sum on range $[L, R]$ using overlaps:
Left interval sum + Right interval sum.
The overlapping middle part is added **twice**. You would need to subtract the intersection, but finding the intersection sum requires another query... which leads to infinite recursion or just using a Prefix Sum array instead.

## Final Recap
1.  **Sparse Table** solves static range queries for idempotent functions.
2.  **Structure:** A 2D array where `st[i][j]` is the value of range starting at $i$ with length $2^j$.
3.  **Build:** Dynamic Programming based on powers of 2. $O(N \log N)$.
4.  **Query:** Combine two overlapping ranges of length $2^k$. $O(1)$.

---

Based on the image provided, here is a detailed breakdown of each Question and Answer about the **Sparse Table** data structure.

---

### Q1: What is the primary limitation of a Sparse Table?
**Answer:** The array must be **immutable** (elements cannot change after construction).

#### **Detailed Explanation**
The word "Immutable" means "cannot be changed."
Sparse Tables are "Static Data Structures." Once you build the table, you cannot efficiently update a value in the original array (like changing `arr[5] = 99`).

**Why is this a limitation?**
Because a single element in the original array contributes to **many** cells in the Sparse Table.
If you have an array of size $N=1000$ and you change one number at index 0, that number is part of:
1.  The range of length 1 starting at 0.
2.  The range of length 2 starting at 0.
3.  The range of length 4 starting at 0.
4.  ...all the way up to the range of length 512.

To update the table for a single change, you would have to re-calculate extensive portions of the table, which takes $O(N)$ time in the worst case. This defeats the purpose of using a fast structure. If you need updates (Dynamic Range Queries), you should use a **Segment Tree** or **Fenwick Tree** instead.

---

### Q2: What is the time complexity to build a Sparse Table for an array of size $N$?
**Answer:** $O(N \log N)$.

#### **Detailed Explanation**
The Sparse Table is essentially a 2D matrix, often denoted as `st[N][K]`.
*   **Dimensions:**
    *   **Rows ($N$):** There is a row for every starting index in the array.
    *   **Columns ($K$):** There is a column for every power of 2 that fits inside $N$. The maximum power is $\log_2 N$.
*   **Filling the Cells:**
    *   Calculating the value of one cell (e.g., `st[i][j]`) takes $O(1)$ time because it just compares two values from the previous column: $\min(\text{val1}, \text{val2})$.

**The Math:**
$$ \text{Total Operations} = (\text{Number of Rows}) \times (\text{Number of Columns}) $$
$$ \text{Total Operations} = N \times \log_2 N $$
$$ \text{Complexity} = O(N \log N) $$

**Example:**
If $N = 1,000,000$ (1 million):
*   $\log_2(1,000,000) \approx 20$.
*   We perform roughly $20 \times 1,000,000 = 20,000,000$ operations.
*   This is very fast for a modern computer (takes less than a second).

---

### Q3: What is the time complexity for Range Minimum Query (RMQ) in a Sparse Table?
**Answer:** $O(1)$.

#### **Detailed Explanation**
$O(1)$ means **Constant Time**. It takes the exact same amount of time to find the minimum of a range of size 5 as it does for a range of size 500,000.

Unlike a simple loop (which scans every element) or a Segment Tree (which traverses a tree structure), the Sparse Table query performs a fixed set of mathematical steps:
1.  Calculate the log length ($k$).
2.  Look up value A.
3.  Look up value B.
4.  Compare A and B.

There are no loops involved in the query phase. This makes Sparse Table the fastest possible algorithm for static range minimum queries.

---

### Q4: Why does Sparse Table allow $O(1)$ query for Minimum but not for Sum?
**Answer:** Minimum is an **idempotent** operation ($\min(x, x) = x$), allowing overlapping ranges. Sum is not.

#### **Detailed Explanation**
This is the core "magic" of the Sparse Table. We cover a range $[L, R]$ using two blocks of length $2^k$. These blocks almost always **overlap**.

**The Idempotency Property:**
An operation is idempotent if applying it to the same value twice gives the same result.
*   **Min:** $\min(5, 5) = 5$ (Idempotent)
*   **GCD:** $\text{gcd}(12, 12) = 12$ (Idempotent)
*   **Sum:** $5 + 5 = 10$ (NOT Idempotent)

**Visual Example:**
Imagine an array: `[10, 20, 5, 30]`. We want the result for the range `[0, 3]`.
We use two overlapping blocks:
1.  **Block A (Indices 0-2):** Values `[10, 20, 5]`
2.  **Block B (Indices 1-3):** Values `[20, 5, 30]`

Notice that **indices 1 and 2 (values 20 and 5)** are inside *both* blocks.

**Using Minimum:**
*   Min(Block A) = 5
*   Min(Block B) = 5
*   Total Min = $\min(5, 5) = 5$.
*   **Result:** Correct. Including 5 twice doesn't hurt.

**Using Sum:**
*   Sum(Block A) = $10 + 20 + 5 = 35$
*   Sum(Block B) = $20 + 5 + 30 = 55$
*   Total Sum = $35 + 55 = 90$.
*   **Actual Sum:** $10+20+5+30 = 65$.
*   **Result:** Wrong. The intersection (25) was added twice.

---

### Q5: Formulated, how do you find $\min(L, R)$ using Sparse Table with precomputed powers of 2?
**Answer:** Let $k = \lfloor \log_2(R - L + 1) \rfloor$. Answer is $\min(st[k][L], st[k][R - 2^k + 1])$.

*(Note: The image uses `st[k][L]` notation. In standard implementations, `k` is usually the second dimension, i.e., `st[L][k]`, but the logic is identical).*

#### **Detailed Explanation**
This formula tells us exactly which two blocks to compare to cover the range $[L, R]$.

1.  **Calculate $k$:**
    $R - L + 1$ is the length of the range.
    $k$ is the largest power of 2 that fits in that length.
    *   *Example:* If range length is 13, $k = 3$ (because $2^3 = 8$ fits, but $2^4 = 16$ is too big).

2.  **First Block (`st[k][L]`):**
    This block starts at the very beginning of our range ($L$) and stretches to the right for length $2^k$.
    *   *Example:* Covers indices $[L, L + 7]$.

3.  **Second Block (`st[k][R - 2^k + 1]`):**
    This block is calculated to **end exactly at $R$**.
    *   Starting position calculation: If we want the block to end at $R$ and it has length $2^k$, it must start at $R - 2^k + 1$.
    *   *Example:* Covers indices $[R - 7, R]$.

**Python Example Trace:**
Array indices `0, 1, 2, 3, 4`. Query range `[0, 4]` (Length 5).
$k = \lfloor \log_2(5) \rfloor = 2$. (Block length $2^2 = 4$).

*   **Left Interval:** Starts at **0**, Length 4. Covers indices `0, 1, 2, 3`.
*   **Right Interval:** Starts at $4 - 4 + 1 = \mathbf{1}$. Length 4. Covers indices `1, 2, 3, 4`.
*   **Union:** `{0, 1, 2, 3}` $\cup$ `{1, 2, 3, 4}` = `{0, 1, 2, 3, 4}`.
*   Every element is covered! Indices 1, 2, 3 are checked twice, but that's okay (Idempotency).
