
# 🧠 Python Lists

## ⚡ What Are Lists?

* **Dynamic arrays** in Python.
* Can hold *anything*—ints, strings, floats, your crushed hopes after failing a test case.

```python
nums = [1, 2, 3]
mixed = [1, "two", 3.0, [4]]
```

---

## 🔧 Basic Operations

```python
# Indexing
nums[0]       # First element
nums[-1]      # Last element

# Slicing
nums[1:3]     # [2, 3] – end index is EXCLUDED
nums[:2]      # [1, 2]
nums[::-1]    # Reverse list

# Length
len(nums)

# Adding
nums.append(4)
nums.insert(1, 10)      # insert at index 1

# Removing
nums.pop()              # removes last element
nums.pop(0)             # removes first
nums.remove(2)          # remove first instance of value 2

# Search
2 in nums               # True/False
nums.index(2)           # returns index of value

# Count
nums.count(2)
```

---

## 🔁 Looping Through Lists

```python
for x in nums:
    print(x)

for i in range(len(nums)):
    print(i, nums[i])

for i, val in enumerate(nums):
    print(i, val)
```

---

## 🧹 List Comprehensions (Sexy AF)

```python
squares = [x*x for x in range(10)]
evens = [x for x in nums if x % 2 == 0]
matrix = [[0]*3 for _ in range(3)]  # 3x3 zero matrix
```

---

## 💥 Common Pitfalls

```python
# WRONG: all rows point to same list
bad_matrix = [[0]*3]*3  

# RIGHT:
good_matrix = [[0]*3 for _ in range(3)]
```

---

## 🎨 Formatting & Printing

```python
print(', '.join(map(str, nums)))    # "1, 2, 3"
' '.join([str(x) for x in nums])    # same as above
print(*nums)                        # 1 2 3 (unpacks list)
```

---

## 🧪 Useful Built-in Functions

```python
sum(nums)
max(nums)
min(nums)
sorted(nums)                        # returns new list
sorted(nums, reverse=True)
list(reversed(nums))
```

---

## 📦 Libraries to Know

### `collections`

```python
from collections import Counter, deque, defaultdict

# Counter
Counter(nums)                       # frequency map

# Deque (fast queue)
dq = deque([1,2,3])
dq.appendleft(0)
dq.pop()
dq.popleft()

# Defaultdict
graph = defaultdict(list)
graph[0].append(1)
```

---

### `itertools`

```python
from itertools import permutations, combinations, product

list(permutations([1,2,3]))         # all perms
list(combinations([1,2,3], 2))      # all 2-combos
list(product([0,1], repeat=3))      # binary combos
```

---

### `heapq`

```python
import heapq

heap = []
heapq.heappush(heap, 3)
heapq.heappush(heap, 1)
heapq.heappop(heap)                # returns smallest

# Max-heap (invert values)
heapq.heappush(heap, -x)
```

---

## 🔄 2D Lists (LeetCode Dungeon Levels)

```python
grid = [[1,2,3],[4,5,6],[7,8,9]]

# Access
grid[0][1]

# Traverse
for row in grid:
    for val in row:
        print(val)
```

---

## 🧠 Advanced Good-To-Know

```python
# Flatten 2D list
flat = [val for row in grid for val in row]

# Remove duplicates
list(set(nums))

# Sorting with key
words.sort(key=lambda x: (len(x), x))

# Binary Search (bisect)
from bisect import bisect_left
i = bisect_left(nums, 3)   # index to insert 3
```

---

## 💪 LC Must-Know Patterns

| Pattern               | Use Case                             |
| --------------------- | ------------------------------------ |
| Sliding Window        | Subarrays, max/min in window         |
| Two Pointers          | Sorted arrays, move inward           |
| Binary Search         | Sorted lists, search insert position |
| Prefix Sum            | Range sums, subarrays                |
| Backtracking          | Permutations, subsets                |
| DFS/BFS               | Graphs, islands, shortest path       |
| Heap / Priority Queue | Top-K, scheduling, greedy problems   |
| HashMap / Counter     | Frequencies, groupings, fast lookup  |

---

## 🧘 TL;DR Summary (aka Lazy Mode)

* Use **list comprehension** for speed & flex.
* Use `deque` for fast pops from both ends.
* Use `Counter`, `defaultdict` for freq & maps.
* Always initialize **2D arrays** with comprehension.
* **Sort with `key`**, use `heapq` for priority queues.
* **Printing?** `print(*arr)` or `' '.join(map(str, arr))`
* Want to impress? Use `itertools` like a boss.

---

# 🧵 Python Strings

---

## 🧠 Basics: What is a String?

* Immutable sequence of characters.
* Yes, *immutable*—no in-place changes. Treat it like your ex: admire from afar, copy if needed.

```python
s = "hello"
s[0]          # 'h'
len(s)        # 5
```

---

## 🔁 Iteration

```python
for ch in s:
    print(ch)

for i, ch in enumerate(s):
    print(i, ch)
```

---

## 🔨 String Methods (THE POWER TOOLS)

```python
s.lower()               # 'hello'
s.upper()               # 'HELLO'
s.capitalize()          # 'Hello'
s.title()               # 'Hello World'
s.strip()               # removes leading/trailing spaces
s.lstrip(), s.rstrip()
```

---

## 🔍 Searching & Replacing

```python
s.find("l")             # index of first 'l'
s.rfind("l")            # last occurrence
s.index("e")            # like find, but errors if not found
s.replace("l", "x")     # 'hexxo'

"he" in s               # True
s.startswith("he")      # True
s.endswith("lo")        # True
```

---

## ✂️ Slicing Strings

```python
s[1:4]          # 'ell'
s[:3]           # 'hel'
s[::2]          # 'hlo'
s[::-1]         # 'olleh' ← Reverse string
```

---

## 🔗 Concatenation & Joining

```python
"ab" + "cd"             # 'abcd'
" ".join(["a", "b", "c"])  # 'a b c'
",".join(list("abc"))     # 'a,b,c'
```

---

## 🛠️ String Formatting

```python
name = "Ash"
f"Hello, {name}!"        # f-string → 'Hello, Ash!'

# Old style
"Hi %s" % name

# format method
"Hi {}".format(name)

# Padding & Alignment
f"{name:>10}"            # right align
f"{name:<10}"            # left align
f"{name:^10}"            # center
```

---

## 🧮 Counting & Frequency

```python
s.count("l")             # 2

from collections import Counter
Counter(s)               # Counter({'l': 2, 'h': 1, 'e': 1, 'o': 1})
```

---

## 📏 Substrings & Palindromes

```python
s[i:j]                  # substring s[i] to s[j-1]
s == s[::-1]            # is palindrome
```

---

## 🧪 Checking Characters

```python
s.isalpha()             # all letters
s.isdigit()             # all numbers
s.isalnum()             # letters + numbers
s.isspace()             # all whitespace
s.islower(), s.isupper()
```

---

## 🧱 Converting Between Types

```python
str(123)                # '123'
int("123")              # 123
ord("a")                # 97
chr(97)                 # 'a'
```

---

## 💬 ASCII & Character Math

```python
# 'a' to 'z' = 97 to 122
# 'A' to 'Z' = 65 to 90

ord("a") + 1            # 98
chr(98)                 # 'b'
```

---

## 🧠 Common Patterns

### Reverse a string

```python
s[::-1]
"".join(reversed(s))
```

### Check Anagram

```python
Counter(s1) == Counter(s2)
sorted(s1) == sorted(s2)
```

### Group Anagrams

```python
from collections import defaultdict

res = defaultdict(list)
for word in words:
    key = tuple(sorted(word))
    res[key].append(word)
```

---

## 🧰 Regular Expressions (for the masochists)

```python
import re

re.findall(r"\d+", s)      # all numbers
re.sub(r"\s+", "", s)      # remove all whitespace
re.match(r"abc", s)
```

---

## 💥 Common String Problems on LeetCode

| Pattern            | Problem Type Example                        |
| ------------------ | ------------------------------------------- |
| Two pointers       | Palindromes, reverse vowels, is subsequence |
| Sliding window     | Longest substring without repeat, anagrams  |
| HashMap + Window   | Longest repeating, minimum window           |
| Stack              | Valid parentheses, decoding strings         |
| Trie / Prefix Tree | StartsWith, autocomplete, word search       |

---

## 🧘 TL;DR Lazy Genius Mode

* Use `s[::-1]` to reverse
* Use `Counter(s)` for frequency
* `in`, `find()`, `replace()` are your go-tos
* Use `join()` and `split()` like a boss
* Format strings with `f""` (fight anyone using `%`)
* Use `.strip()` like you're removing bad vibes

---

