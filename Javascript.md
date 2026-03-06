# JavaScript One-Liners Cheat Sheet

Practical JavaScript one-liners for day-to-day coding.

## Quick Start

```bash
$ node --version
$ node -e "console.log('Hello, world!')"
$ node -e "console.log([...Array(101).keys()].reduce((a, b) => a + b, 0))"  # 5050
```

## Variables and Assignment

```javascript
// Swap variables
let a = 10;
let b = 20;
[a, b] = [b, a];

// Multiple assignments
const [x, y, z] = [1, 2, 3];
```

## Strings and Reversal

```javascript
// Reverse string/array
const s = "javascript";
const revS = [...s].reverse().join("");

const arr = [1, 2, 3, 4];
const revArr = [...arr].reverse();

// Palindrome check
const pal = "radar";
const isPalindrome = pal === [...pal].reverse().join("");
```

## Multiplying Iterables

```javascript
const repeated = "A".repeat(3); // 'AAA'
const filled = Array(4).fill(1); // [1, 1, 1, 1]
```

## Conditional Expressions (Ternary)

```javascript
const num = 3;
const label = num % 2 === 1 ? "Odd" : "Even";
console.log(label);
```

## Join and Print Formatting

```javascript
const list = [1, 2, 3, 4];

const csv = list.join(", ");
console.log(list.join(", ") + ".");
```

## Default Values in Objects

```javascript
const user = { name: "ABC", age: 8 };

const value1 = user.abc; // undefined
const value2 = user.abc ?? "DEFAULT"; // DEFAULT
```

## Counting with reduce

```javascript
const list = ["A", "B", "C", "A", "A", "B"];
const counts = list.reduce((acc, x) => ((acc[x] = (acc[x] || 0) + 1), acc), {});

const words = "the quick brown fox jumps over the lazy little dog".split(" ");
const wordCount = words.reduce(
  (acc, w) => ((acc[w] = (acc[w] || 0) + 1), acc),
  {},
);
```

## Entries with Custom Start

```javascript
const items = ["a", "b", "c"];
items.forEach((item, i) => console.log(i - 1, item));
```

## Objects and Destructuring

```javascript
// Merge objects
const o1 = { a: 1 };
const o2 = { b: 2 };
const merged = { ...o1, ...o2 };

// Reverse object (value -> key)
const rev = Object.fromEntries(
  Object.entries({ x: 10, y: 20 }).map(([k, v]) => [v, k]),
);

// Destructuring
const nums = [1, 2, 3];
const [p, q, r] = nums;
const [first, ...middle] = [10, 20, 30, 40];
const last = middle.pop();
```

## Number Formatting

```javascript
const num = 1_000_000_000;
console.log(num.toLocaleString("en-US")); // 1,000,000,000
```

## Useful map/filter/flatMap

```javascript
const nums = [1, 2, 3, 4, 5];

const squares = nums.map((x) => x * x);
const evens = nums.filter((x) => x % 2 === 0);
const squareMap = Object.fromEntries(
  Array.from({ length: 5 }, (_, i) => [i + 1, (i + 1) ** 2]),
);

const flat = [[1, 2], [3, 4], [5]].flatMap((row) => row);
```

## Array One-Liners

```javascript
const nums = [1, 2, 3, 4, 5, 6];

const unique = [...new Set([1, 2, 2, 3, 3, 4])];

const randomItem = nums[Math.floor(Math.random() * nums.length)];

const groupedByParity = Object.groupBy(nums, (n) => (n % 2 ? "odd" : "even"));
```

## map, filter, some, every

```javascript
const vals = ["10", "20", "30"];
const ints = vals.map(Number);

const primes = Array.from({ length: 48 }, (_, i) => i + 2).filter((x) =>
  Array.from({ length: x - 2 }, (_, i) => i + 2).every((y) => x % y !== 0),
);

const hasGt10 = [5, 8, 12].some((x) => x > 10);

const allPositive = [1, 2, 3].every((x) => x > 0);
```

## Object One-Liners

```javascript
const user = { id: 7, name: "Alex", age: 25, city: "Pune" };

const picked = (({ id, name }) => ({ id, name }))(user);

const omitted = (({ age, ...rest }) => rest)(user);

const renamedKeys = Object.fromEntries(
  Object.entries(user).map(([k, v]) => [k.toUpperCase(), v]),
);
```

## Map One-Liners

```javascript
const m = new Map([
  ["a", 1],
  ["b", 2],
  ["c", 3],
]);

const objFromMap = Object.fromEntries(m);

const mapFromObject = new Map(Object.entries({ x: 10, y: 20 }));

const doubledMap = new Map([...m].map(([k, v]) => [k, v * 2]));

const filteredMap = new Map([...m].filter(([, v]) => v >= 2));

const sortedMap = new Map([...m].sort((a, b) => a[1] - b[1]));
```

## Binary and Decimal Conversion

```javascript
const decimal = parseInt("101101", 2);

const binary = (45).toString(2);
```

## Max/Min and Key Functions

```javascript
const words = ["this", "is", "a", "javascript", "cheatsheet"];

const longest = words.reduce((a, b) => (a.length >= b.length ? a : b));

const smallest = Math.min(...[10, 3, 50, 2]);
```

## Method Chaining

```javascript
const text = "  hello javascript  ";

const result = text
  .trim()
  .toLowerCase()
  .replace(/\b\w/g, (c) => c.toUpperCase())
  .replace(/\s+/g, "-"); // 'Hello-Javascript'
```

## Working with Files

```javascript
const fs = require("fs");

fs.writeFileSync("notes.txt", "hello\n");

const text = fs.readFileSync("notes.txt", "utf8");

const lines = fs
  .readFileSync("notes.txt", "utf8")
  .split(/\r?\n/)
  .filter(Boolean);
```

## JSON and Date/Time

```javascript
const obj = { name: "alex", age: 25 };
const jsonStr = JSON.stringify(obj);
const pretty = JSON.stringify(obj, null, 2);
const back = JSON.parse(jsonStr);

const now = new Date();
const nextWeek = new Date(now.getTime() + 7 * 24 * 60 * 60 * 1000)
  .toISOString()
  .slice(0, 10);
```

## Class Magic Methods (Idiomatic JS)

```javascript
class Vector {
  constructor(x, y) {
    this.x = x;
    this.y = y;
  }

  toString() {
    return `Vector(x=${this.x}, y=${this.y})`;
  }

  add(other) {
    return new Vector(this.x + other.x, this.y + other.y);
  }
}
```
