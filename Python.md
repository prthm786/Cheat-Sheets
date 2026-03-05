# Python One-Liners Cheat Sheet

Practical Python one-liners for day-to-day coding.

## Quick Start

```bash
$ python --version
$ python -c "print('Hello, world!')"
$ python -c "print(sum(range(101)))"  # 5050
```

## Variables and Assignment

```python
# Swap variables
a = 10
b = 20
a, b = b, a

# Multiple assignments
a, b, c = 1, 2, 3
```

## Strings and Reversal

```python
# Reverse a string/list using slicing [start:stop:step]
s = "python"
rev_s = s[::-1]

l1 = [1, 2, 3, 4]
rev_l1 = l1[::-1]

# Palindrome check
pal = "radar"
is_palindrome = pal == pal[::-1]
```

## Multiplying Iterables

```python
s1 = "A" * 3           # 'AAA'
l1 = [1] * 4            # [1, 1, 1, 1]
```

## Conditional Expressions (Ternary)

```python
num = 3
label = "Odd" if num % 2 == 1 else "Even"
print(label)
```

## Join and Print Formatting

```python
l1 = [1, 2, 3, 4]

# join() needs strings
csv = ", ".join(map(str, l1))

# Formatted printing
print(*l1, sep=", ", end=".\n")
```

## Default Values in Dict

```python
d1 = {"name": "ABC", "age": 8}

# d1["abc"]  # KeyError
value1 = d1.get("abc")              # None
value2 = d1.get("abc", "DEFAULT") # DEFAULT
```

## Counting with Counter

```python
from collections import Counter

l1 = ["A", "B", "C", "A", "A", "B"]
c1 = Counter(l1)
most_common_3 = c1.most_common(3)

words = "the quick brown fox jumps over the lazy little dog".split()
word_count = Counter(words)
```

## Enumerate with Custom Start

```python
items = ["a", "b", "c"]
for i, item in enumerate(items, start=-1):
    print(i, item)
```

## Dictionaries and Unpacking

```python
# Merge dicts (Python 3.9+)
d1 = {"a": 1}
d2 = {"b": 2}
merged = d1 | d2

# Reverse dict (value -> key)
rev = {v: k for k, v in {"x": 10, "y": 20}.items()}

# Unpacking
nums = [1, 2, 3]
a, b, c = nums
first, *middle, last = [10, 20, 30, 40]
```

## Number Formatting

```python
num = 1_000_000_000
print(f"{num:_}")  # 1_000_000_000
print(f"{num:,}")  # 1,000,000,000
```

## Useful Comprehensions

```python
nums = [1, 2, 3, 4, 5]

squares = [x * x for x in nums]
evens = [x for x in nums if x % 2 == 0]
square_map = {x: x * x for x in range(1, 6)}

flat = [item for row in [[1, 2], [3, 4], [5]] for item in row]
```

## Lambda, Filter, Any, All

```python
vals = ["10", "20", "30"]
ints = list(map(int, vals))

primes = list(filter(lambda x: all(x % y != 0 for y in range(2, x)), range(2, 50)))

has_gt_10 = any(x > 10 for x in [5, 8, 12])
all_positive = all(x > 0 for x in [1, 2, 3])
```

## Binary and Decimal Conversion

```python
decimal = int("101101", 2)
binary = format(45, "b")
```

## Combinations and Permutations

```python
from itertools import combinations, permutations

comb_2 = list(combinations([1, 2, 3, 4], 2))
perm_2 = list(permutations([1, 2, 3, 4], 2))
```

## Max/Min and Key Functions

```python
words = ["this", "is", "a", "python", "cheatsheet"]
longest = max(words, key=len)
smallest = min([10, 3, 50, 2])
```

## Method Chaining

```python
text = "  hello python  "
result = text.strip().title().replace(" ", "-")  # 'Hello-Python'
```

## Quick Debugging with f-Strings

```python
name = "variable"
age = 10
print(f"{name = }")
print(f"{age = }")
```

## Chained Comparisons

```python
a = 7
if 1 < a < 10:
    print(f"a is {a} which is between 1 and 10")
```

## Working with Files

```python
from pathlib import Path

Path("notes.txt").write_text("hello\n")
text = Path("notes.txt").read_text()
lines = Path("notes.txt").read_text().splitlines()

# Alternative
lines2 = open("notes.txt").read().splitlines()
```

## JSON and Date/Time

```python
import json
from datetime import datetime, timedelta

obj = {"name": "alex", "age": 25}
json_str = json.dumps(obj)
pretty = json.dumps(obj, indent=2)
back = json.loads(json_str)

now = datetime.now()
next_week = (now + timedelta(days=7)).strftime("%Y-%m-%d")
```

## Dunder Methods (For Better Classes)

```python
class Vector:
    def __init__(self, x, y):
        self.x = x
        self.y = y

    def __repr__(self):
        return f"Vector(x={self.x}, y={self.y})"

    def __add__(self, other):
        return Vector(self.x + other.x, self.y + other.y)
```
