# Assignment — Utility Function Library

## What You Are Building

A utility function library with an interactive demo page. You will write the same functions three ways (declaration, expression, arrow) and build a UI that uses them.

---

## Requirements

Create `function-library.html` with:

### Part 1 — Write Functions Three Ways

For each of these utilities, write it as a declaration, expression, AND arrow function:

1. `capitalize(str)` — capitalises the first letter of a string
2. `clamp(value, min, max)` — clamps a number between min and max
3. `formatCurrency(amount, currency)` — formats a number as currency (e.g., `$29.99`)

Show all three versions in a code display on the page, and verify they all produce the same output.

### Part 2 — Array Utilities (arrow functions)

Write these as arrow functions and demonstrate them on a sample array:

- `sum(arr)` — returns the sum of all numbers
- `average(arr)` — returns the average
- `max(arr)` — returns the largest number
- `min(arr)` — returns the smallest number
- `range(arr)` — returns max - min

Use the array: `[23, 45, 12, 67, 34, 89, 11, 56]`

### Part 3 — String Utilities (arrow functions)

Write these as arrow functions:

- `truncate(str, maxLength)` — truncates a string and adds `...` if too long
- `slugify(str)` — converts "Hello World" to "hello-world"
- `countWords(str)` — counts the number of words in a string
- `isPalindrome(str)` — returns true if the string reads the same forwards and backwards

### Part 4 — Interactive Demo

Build a UI where the user can:
- Type a string and see `capitalize`, `truncate`, `slugify`, `countWords`, and `isPalindrome` applied in real time
- Type a number and see `clamp(value, 0, 100)` applied
- Type a comma-separated list of numbers and see all array utilities applied

---

## What Good Looks Like

- All three function styles (declaration, expression, arrow) are demonstrated
- The interactive demo updates in real time as the user types
- Functions handle edge cases (empty string, empty array, non-number input)
- Code is clean and well-commented

---

## Submission

Submit `function-library.html`.
