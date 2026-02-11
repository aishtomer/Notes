# Minimum Stacks and Minimum Queues.

To understand these data structures, we cannot simply jump into the code. We must build the foundation. We will start with the basic data structures (Stack and Queue), discuss the concept of "Amortized Complexity," move to Monotonic Stacks, and finally construct the Min Stack and Min Queue.

---

## Part 1: The Prerequisites

Before we build "Minimum" versions, we must master the standard versions.

### 1. The Stack (LIFO)
A **Stack** is a linear data structure that follows the **LIFO** (Last In, First Out) principle. Imagine a stack of plates; you place a new plate on top, and if you need a plate, you take the one from the top.

**Key Operations:**
1.  **Push:** Add an element to the top.
2.  **Pop:** Remove the top element.
3.  **Top (or Peek):** Look at the top element without removing it.

**Complexity:**
*   Push/Pop/Top: $O(1)$ (Constant time).

**Python Implementation:**
In Python, a simple `list` acts as a stack.
*   `append()` is Push.
*   `pop()` is Pop.
*   `[-1]` is Top.

```python
stack = []
stack.append(10) # Stack: [10]
stack.append(20) # Stack: [10, 20]
print(stack[-1]) # Output: 20
stack.pop()      # Stack: [10]
```

### 2. The Queue (FIFO)
A **Queue** follows the **FIFO** (First In, First Out) principle. Imagine a line at a ticket counter. The first person to join the line is the first one served.

**Key Operations:**
1.  **Enqueue:** Add an element to the back (rear).
2.  **Dequeue:** Remove the element from the front.

**Complexity:**
*   Enqueue/Dequeue: $O(1)$.

**Python Implementation:**
Using a Python `list` for a queue is inefficient because removing from the front (`pop(0)`) requires shifting all other elements, making it $O(N)$. Instead, we use `collections.deque` (Doubly Ended Queue).

```python
from collections import deque

queue = deque()
queue.append(10)      # Enqueue: [10]
queue.append(20)      # Enqueue: [10, 20]
queue.popleft()       # Dequeue: 10 removed. Queue: [20]
```

### 3. The Constraint of Standard Structures
Standard Stacks and Queues give us access to data in specific orders ($O(1)$). However, if we want to know the **Minimum Element** currently inside the structure, we hit a wall.

To find the minimum in a standard Stack/Queue, we must iterate through all elements:
*   **Time Complexity:** $O(N)$ (Linear time).

**The Goal:** We want to design a Stack and a Queue that support `push`, `pop`, and `get_min` (or equivalent) all in **$O(1)$ time**.

---

## Part 2: The Minimum Stack (Min Stack)

### The Problem
Design a Data Structure that supports:
1.  `push(x)`: Push element x onto stack.
2.  `pop()`: Removes the element on top of the stack.
3.  `top()`: Get the top element.
4.  `getMin()`: Retrieve the minimum element in the stack.

**All operations must be $O(1)$.**

### Approach 1: The "Two Stacks" Method (Recommended)

We cannot simply store a single variable `current_min`. Why?
*   Imagine the stack is `[5, 2]`. `current_min` is 2.
*   If we pop `2`, the stack becomes `[5]`. The minimum should revert to 5.
*   A single variable cannot "remember" what the previous minimum was.

**The Solution:** We use **memory** to trade for time. We maintain **two** stacks:
1.  **Main Stack:** Stores the actual data.
2.  **Min Stack:** Stores the minimums corresponding to the state of the main stack.

#### The Logic
*   **Push(x):**
    *   Push `x` to `Main Stack`.
    *   Check `Min Stack`. If `Min Stack` is empty OR `x <= Min Stack.top()`, push `x` to `Min Stack`.
    *   *Concept:* This means "With the addition of x, the new current minimum is x."
*   **Pop():**
    *   Pop element `val` from `Main Stack`.
    *   If `val == Min Stack.top()`, it means we are removing the current minimum. We must also pop from `Min Stack`.
    *   *Concept:* We are reverting to the previous minimum.
*   **GetMin():**
    *   Simply return `Min Stack.top()`.

#### Detailed Walkthrough
Operations: `Push(5)`, `Push(6)`, `Push(3)`, `Push(7)`, `Pop()`, `Pop()`.

1.  **Push(5):**
    *   Main: `[5]`
    *   MinStack: `[5]` (Empty, so push 5)
2.  **Push(6):**
    *   Main: `[5, 6]`
    *   MinStack: `[5]` (6 > 5, so we don't push. 5 is still the min).
3.  **Push(3):**
    *   Main: `[5, 6, 3]`
    *   MinStack: `[5, 3]` (3 < 5, so push 3. New min is 3).
4.  **Push(7):**
    *   Main: `[5, 6, 3, 7]`
    *   MinStack: `[5, 3]` (7 > 3, ignore).
5.  **Pop() -> returns 7:**
    *   Main: `[5, 6, 3]`
    *   7 != MinStack.top() (3). Do not touch MinStack.
    *   Current Min is still 3.
6.  **Pop() -> returns 3:**
    *   Main: `[5, 6]`
    *   3 == MinStack.top() (3). Pop from MinStack!
    *   MinStack: `[5]`
    *   Current Min reverts to 5.

#### Python Implementation

```python
class MinStack:
    def __init__(self):
        # Stores all the data
        self.stack = []
        # Stores the minimums
        self.min_stack = []

    def push(self, val: int) -> None:
        self.stack.append(val)
        
        # If min_stack is empty OR val is smaller than or equal to current min
        if not self.min_stack or val <= self.min_stack[-1]:
            self.min_stack.append(val)

    def pop(self) -> None:
        if not self.stack:
            return
        
        val = self.stack.pop()
        
        # If the item we just removed was the minimum, 
        # remove it from min_stack too.
        if val == self.min_stack[-1]:
            self.min_stack.pop()

    def top(self) -> int:
        return self.stack[-1] if self.stack else None

    def getMin(self) -> int:
        return self.min_stack[-1] if self.min_stack else None

# --- Testing the Code ---
ms = MinStack()
ms.push(-2)
ms.push(0)
ms.push(-3)
print(f"Current Min: {ms.getMin()}") # Returns -3
ms.pop()
print(f"Top: {ms.top()}")      # Returns 0
print(f"Current Min: {ms.getMin()}") # Returns -2 (The min reverted!)
```

### Approach 2: The "Tuple" Method
Instead of two separate lists, we can store tuples in a single list.
Each element in the stack will look like: `(value, current_min_at_this_point)`.

*   **Push(x):** New Min = `min(x, stack.top()[1])`. Push `(x, New Min)`.
*   **GetMin():** Return `stack.top()[1]`.

**Pros:** Simpler logic to write.
**Cons:** Uses more space if duplicates are frequent (Two Stack method saves space by ignoring non-min values).

```python
class MinStackTuple:
    def __init__(self):
        self.stack = []

    def push(self, val: int) -> None:
        if not self.stack:
            self.stack.append((val, val))
        else:
            current_min = self.stack[-1][1]
            self.stack.append((val, min(val, current_min)))

    def pop(self) -> None:
        self.stack.pop()

    def getMin(self) -> int:
        return self.stack[-1][1]
```

---

## Part 3: The Minimum Queue (Min Queue)

This is significantly harder than the Min Stack.
In a Queue, elements are added at the back and removed from the front.
*   If we remove the current minimum from the front, how do we know what the *next* minimum is in the remaining line?

There are two primary ways to solve this.
1.  **Queue using Two Stacks** (General Purpose Data Structure).
2.  **Monotonic Deque** (Optimized for Sliding Window problems).

### Method 1: Min Queue using Two Stacks

This is the standard interview answer for "Design a Queue that supports $O(1)$ min". It relies on the property that **a Queue can be implemented using two Stacks.**

#### The Concept
We maintain two Stacks: `Inbox` and `Outbox`.
*   **Enqueue:** Push onto `Inbox`.
*   **Dequeue:** Pop from `Outbox`.
    *   *Catch:* If `Outbox` is empty, pop **everything** from `Inbox` and push it onto `Outbox`. This reverses the order, effectively turning the LIFO stacks into a FIFO queue.

Since we already know how to make a **Min Stack**, we just make `Inbox` and `Outbox` both **Min Stacks**.

The minimum of the *entire* queue is simply:
$$ \min(\text{Inbox.getMin()}, \text{Outbox.getMin()}) $$

#### Complexity Analysis
*   **Enqueue:** $O(1)$.
*   **Dequeue:** Amortized $O(1)$.
    *   Sometimes it takes $O(N)$ (when moving Inbox to Outbox), but each element is moved exactly once. Over $N$ operations, the average is $O(1)$.
*   **GetMin:** $O(1)$.

#### Python Implementation

First, we assume the `MinStack` class from Part 2 exists.

```python
class MinQueueTwoStacks:
    def __init__(self):
        # We reuse the MinStack class defined previously
        self.inbox = MinStack()
        self.outbox = MinStack()

    def enqueue(self, val: int):
        self.inbox.push(val)

    def dequeue(self):
        # If outbox is empty, dump inbox into it
        if not self.outbox.stack:
            while self.inbox.stack:
                self.outbox.push(self.inbox.top())
                self.inbox.pop()
        
        return self.outbox.pop()

    def getMin(self):
        # Check both stacks
        min_in = self.inbox.getMin()
        min_out = self.outbox.getMin()

        if min_in is None and min_out is None:
            return None
        if min_in is None:
            return min_out
        if min_out is None:
            return min_in
        
        return min(min_in, min_out)

# --- Test ---
mq = MinQueueTwoStacks()
mq.enqueue(10)
mq.enqueue(5)
mq.enqueue(20)
print(f"Queue Min: {mq.getMin()}") # 5 (from inbox)

mq.dequeue() # Removes 10. Internally moves 5, 20 to outbox.
# Outbox: [20, 5] (Top is 5). Inbox: []

print(f"Queue Min: {mq.getMin()}") # 5 (from outbox)
mq.dequeue() # Removes 5.
print(f"Queue Min: {mq.getMin()}") # 20
```

---

### Method 2: Monotonic Queue (The Sliding Window King)

The Two-Stack method is great for a general data structure. However, in algorithm problems like **"Sliding Window Minimum,"** we often use a different approach called a **Monotonic Queue** (implemented via a Deque).

#### What is a Monotonic Queue?
It is a queue where the elements are always sorted (monotonically increasing or decreasing).
For a **Min Queue**, we want the elements inside our deque to be **increasing**.

**The Rule:**
The front of the deque will ALWAYS be the minimum of the current window.

#### The Algorithm
When we add a new element `X`:
1.  **Maintain Order:** Check the back of the deque. If the last element is **greater** than `X`, it is useless. Why? Because `X` is smaller and `X` arrived *later*. The larger element at the back will never be the minimum again while `X` is present.
2.  **Pop useless elements:** Keep popping from the back until the back element is $\le X$ (or deque is empty).
3.  **Push:** Add `X` to the back.

When we remove an element (because the sliding window moved):
1.  Check if the element leaving the window is the one at the **front** of the deque.
2.  If yes, `popleft()`. If no, do nothing (it was already removed in step 2 of insertion previously).

#### Detailed Trace: Sliding Window Minimum
Array: `[1, 3, -1, -3, 5, 3, 6, 7]`, Window Size ($k$) = 3.

**Window 1: `[1, 3, -1]`**
1.  Add 1: Deque `[1]`
2.  Add 3: 3 > 1. Keep it. Deque `[1, 3]`
3.  Add -1: -1 < 3 (pop 3), -1 < 1 (pop 1). Push -1. Deque `[-1]`
    *   **Min:** `deque[0]` -> **-1**

**Window 2: `[3, -1, -3]`** (Slide right)
1.  Remove 1: 1 is not at `deque[0]` (-1). Do nothing.
2.  Add -3: -3 < -1 (pop -1). Push -3. Deque `[-3]`
    *   **Min:** **-3**

**Window 3: `[-1, -3, 5]`**
1.  Remove 3: Not at front.
2.  Add 5: 5 > -3. Keep. Deque `[-3, 5]`
    *   **Min:** **-3**

**Window 4: `[-3, 5, 3]`**
1.  Remove -1: Not at front.
2.  Add 3: 3 < 5 (pop 5). 3 > -3 (keep). Deque `[-3, 3]`
    *   **Min:** **-3**

**Window 5: `[5, 3, 6]`**
1.  Remove -3: **Yes!** -3 is at `deque[0]`. PopLeft. Deque `[3]`
2.  Add 6: 6 > 3. Deque `[3, 6]`
    *   **Min:** **3**

#### Python Implementation (Sliding Window)

This is the standard solution for LeetCode 239: Sliding Window Maximum (reversed logic for Min).

```python
from collections import deque

def sliding_window_minimum(nums, k):
    dq = deque() # Stores INDICES, not values (easier to check window bounds)
    result = []
    
    for i in range(len(nums)):
        # 1. Remove elements out of the current window from the front
        # The window is [i - k + 1, i]. If index < i - k + 1, it's out.
        if dq and dq[0] < i - k + 1:
            dq.popleft()
            
        # 2. Maintain Monotonicity: Remove elements from back 
        # that are greater than current element (useless for Min)
        while dq and nums[dq[-1]] > nums[i]:
            dq.pop()
            
        # 3. Add current index
        dq.append(i)
        
        # 4. If we have hit the window size, record result
        # (i starts at 0, so result starts when i >= k-1)
        if i >= k - 1:
            result.append(nums[dq[0]])
            
    return result

# --- Test ---
arr = [1, 3, -1, -3, 5, 3, 6, 7]
k = 3
print(f"Input: {arr}")
print(f"Sliding Window Mins: {sliding_window_minimum(arr, k)}")
# Output should match our manual trace: [-1, -3, -3, -3, 3, 3]
```

---

## Summary and Comparison

| Structure | Main Idea | Time Complexity (Push/Pop/Min) | Space Complexity | Best Use Case |
| :--- | :--- | :--- | :--- | :--- |
| **Min Stack** | Main Stack + Aux Stack (MinStack) | $O(1)$ | $O(N)$ | Tracking Min in LIFO history (e.g., recursive calls). |
| **Min Queue (2 Stacks)** | Inbox Stack + Outbox Stack | Amortized $O(1)$ | $O(N)$ | General "Queue" behavior where you need min. |
| **Monotonic Queue** | Deque maintaining sorted order | Amortized $O(1)$ | $O(k)$ (Window size) | Sliding Window problems (fixed range). |

#### Why use Monotonic Queue over Two Stacks for Sliding Windows?
While the Two-Stack MinQueue can solve sliding windows, the Monotonic Deque is often preferred because:
1.  It stores indices, making it easier to handle window bounds.
2.  It doesn't require "moving" elements between stacks (though the amortized complexity is the same, constant factors are often lower).
3.  It explicitly handles the "Sliding" nature by popping from the front based on index logic.

---

### Q1: How do you modify a stack to support finding the minimum element in $O(1)$?
**Answer from image:** Store pairs `(element, min_so_far)` instead of just elements.

#### **Detailed Explanation**
A standard stack keeps track of elements in "Last-In, First-Out" order. It remembers history, but it doesn't prioritize value magnitude.

If you push `[5, 2, 8]`, the stack looks like this:
1.  Bottom: 5
2.  Middle: 2
3.  Top: 8

If you ask for the minimum, you have to scan all three ($O(N)$). To make this $O(1)$, we need the stack to "remember" what the minimum was at every single step of its growth.

**The "Pairs" Strategy:**
Instead of storing just the integer `x`, we store a tuple: `(x, minimum_of_stack_after_x_is_added)`.

**Walkthrough:**
1.  **Push 5:** Stack is empty. Min is 5. Store `(5, 5)`.
2.  **Push 2:** Current min is 5. New value is 2. `min(5, 2) = 2`. Store `(2, 2)`.
3.  **Push 8:** Current min is 2. New value is 8. `min(2, 8) = 2`. Store `(8, 2)`.

**Stack State:** `[(5, 5), (2, 2), (8, 2)]`

Now, if you want the minimum, you just look at the second item of the top tuple.
*   `top()` gives `(8, 2)`. The min is **2**.
*   `pop()` removes `(8, 2)`.
*   New `top()` is `(2, 2)`. The min is **2**.
*   `pop()` removes `(2, 2)`.
*   New `top()` is `(5, 5)`. The min is **5** (The min correctly reverted!).

#### **Python Example**
```python
class MinStackPairs:
    def __init__(self):
        self.stack = [] # Will store tuples (val, current_min)

    def push(self, val):
        if not self.stack:
            self.stack.append((val, val))
        else:
            # Look at the min of the element below
            current_min = self.stack[-1][1]
            new_min = min(val, current_min)
            self.stack.append((val, new_min))

    def get_min(self):
        if not self.stack: return None
        return self.stack[-1][1] # O(1) Access

# Test
ms = MinStackPairs()
ms.push(5); ms.push(2); ms.push(8)
print(ms.get_min()) # Output: 2
```

---

### Q2: How can you implement a Minimum Queue using two stacks?
**Answer from image:** Use an input stack (`s1`) and an output stack (`s2`). When `s2` is empty during a pop/top operation, move all elements from `s1` to `s2` (reversing them). The minimum is $\min(s1.min, s2.min)$.

#### **Detailed Explanation**
A Queue is FIFO (First-In, First-Out). A Stack is LIFO (Last-In, First-Out).
If you pour a stack into another stack, the order reverses. Two reversals = Original Order.

**The Architecture:**
*   **Inbox Stack (`s1`):** Handles all `enqueue` operations.
*   **Outbox Stack (`s2`):** Handles all `dequeue` operations.

**The Logic:**
1.  **Enqueue:** Always push onto `s1`.
2.  **Dequeue:** Pop from `s2`.
    *   *Problem:* What if `s2` is empty?
    *   *Solution:* We dump the *entire* contents of `s1` into `s2`. This reverses the order, putting the "oldest" element (which was at the bottom of `s1`) onto the top of `s2`, ready to be popped.
3.  **Find Minimum:** Since both `s1` and `s2` are implemented as **Min Stacks** (from Q1), we know the minimum of the "new stuff" (`s1`) and the minimum of the "old stuff" (`s2`). The global minimum is the smaller of the two.

#### **Python Example**
```python
class MinQueue:
    def __init__(self):
        # We use the MinStack class defined in Q1
        self.s1 = MinStackPairs() # Inbox
        self.s2 = MinStackPairs() # Outbox

    def enqueue(self, val):
        self.s1.push(val)

    def dequeue(self):
        if not self.s2.stack:
            # Move everything from s1 to s2
            while self.s1.stack:
                val, _ = self.s1.stack.pop() # Pop from s1
                self.s2.push(val)            # Push to s2
        
        # Pop from s2 (which is now in FIFO order)
        if self.s2.stack:
            self.s2.stack.pop()

    def get_min(self):
        min1 = self.s1.get_min()
        min2 = self.s2.get_min()
        
        if min1 is None: return min2
        if min2 is None: return min1
        return min(min1, min2)
```

---

### Q3: What is the amortized complexity of the 2-stack Minimum Queue implementation?
**Answer from image:** $O(1)$ per operation (each element is pushed/popped at most twice).

#### **Detailed Explanation**
"Amortized" complexity refers to the average cost per operation over a long sequence of operations.

If you look at `dequeue` in the code above, it contains a `while` loop.
*   **Worst Case:** If `s1` has $N$ elements and `s2` is empty, `dequeue` takes $O(N)$ time because it moves everything.
*   **Best Case:** If `s2` has items, `dequeue` takes $O(1)$ time.

**Why is it $O(1)$ overall?**
Let's track the "Life Cycle" of a single element, let's call it `Item A`.
1.  `Item A` is pushed onto `s1`. (**1 Push**)
2.  Eventually, `Item A` is popped from `s1` inside the `while` loop. (**1 Pop**)
3.  `Item A` is immediately pushed onto `s2`. (**1 Push**)
4.  Eventually, `Item A` is dequeued (popped) from `s2`. (**1 Pop**)

No matter what happens, `Item A` is touched exactly **4 times** in its entire life.
If we process $N$ elements, the total operations are $4N$.
Average Cost = $\frac{4N}{N} = 4$.
In Big-O notation, constants are ignored, so the complexity is **$O(1)$**.

---

### Q4: How can Minimum Queue be used to find the sliding window minimum of length $M$ in an array of size $N$?
**Answer from image:** Push elements to the Min Queue. Once size > $M$, pop from front. The current minimum is always available. Total complexity $O(N)$.

#### **Detailed Explanation**
This is a classic problem: Given `[10, 20, 5, 8, 3]` and window size $M=2$.
We need to slide a window across and report the minimum at every step.

**The Algorithm using Min Queue:**
We treat the sliding window as a Queue.
1.  **Add** the new element entering the window (Enqueue).
2.  **Remove** the old element leaving the window (Dequeue).
3.  **Report** the minimum of the current Queue.

Because our MinQueue allows all three of these operations in $O(1)$, we can process the whole array in linear time.

**Walkthrough `[10, 20, 5]` with Window `M=2`**:

1.  **Start:** Queue `[]`
2.  **i=0 (Val 10):** Enqueue 10. Queue `[10]`. Size is 1 (< M).
3.  **i=1 (Val 20):** Enqueue 20. Queue `[10, 20]`. Size is 2 (= M).
    *   **Get Min:** 10.
    *   **Slide:** To move to next step, Dequeue 10. Queue `[20]`.
4.  **i=2 (Val 5):** Enqueue 5. Queue `[20, 5]`. Size is 2 (= M).
    *   **Get Min:** 5.
    *   **Slide:** Dequeue 20. Queue `[5]`.

#### **Python Example**
```python
def sliding_window_min(arr, m):
    mq = MinQueue() # The class we built in Q2
    result = []
    
    # Fill first M-1 elements to start the window
    for i in range(m - 1):
        mq.enqueue(arr[i])
        
    # Slide the window
    for i in range(m - 1, len(arr)):
        # 1. Add new element
        mq.enqueue(arr[i])
        
        # 2. Record the minimum
        result.append(mq.get_min())
        
        # 3. Remove the element that is falling out of the window
        # Note: In a real implementation with just values, we trust 
        # the order. The element we dequeue is guaranteed to be arr[i - m + 1]
        mq.dequeue()
        
    return result

# Test
arr = [10, 20, 5, 8, 3]
# Window [10, 20] -> Min 10
# Window [20, 5]  -> Min 5
# Window [5, 8]   -> Min 5
# Window [8, 3]   -> Min 3
print(sliding_window_min(arr, 2)) # Output: [10, 5, 5, 3]
```
