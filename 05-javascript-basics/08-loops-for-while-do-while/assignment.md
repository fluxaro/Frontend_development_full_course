# Assignment — Number Patterns and FizzBuzz

## What You Are Building

An interactive page that generates number patterns, runs FizzBuzz, and simulates a dice game — demonstrating all three loop types.

---

## Requirements

Create `loops-app.html` with:

### Part 1 — FizzBuzz (for loop)

- A number input for the upper limit (default 30)
- A "Run FizzBuzz" button
- Display results in a grid of coloured pills:
  - FizzBuzz → purple
  - Fizz → blue
  - Buzz → green
  - Number → grey

### Part 2 — Multiplication Table (nested for loops)

- A number input (1–12)
- A "Show Table" button
- Display the full 12-row multiplication table for that number
- Highlight multiples that are also multiples of 10

### Part 3 — Countdown Timer (while loop)

- A number input for seconds (1–60)
- A "Start Countdown" button
- Display the countdown updating every second using `setInterval`
- Show "🚀 Launch!" when it reaches 0
- A "Stop" button to cancel the countdown

### Part 4 — Dice Game (do-while)

- A "Roll Until 6" button
- Roll a virtual dice repeatedly until a 6 appears
- Display each roll result
- Show the total number of rolls it took
- Show the probability: `1/rolls` formatted as a percentage

### Part 5 — Sum Calculator (for loop with break)

- Two number inputs: start and end of a range
- A "Calculate" button
- Sum all numbers in the range
- Also find the first number in the range divisible by both 7 and 11 (use `break`)

---

## What Good Looks Like

- FizzBuzz grid is colourful and easy to read
- Countdown actually counts down in real time
- Dice game shows each individual roll
- All loops use the appropriate type (`for`, `while`, `do-while`)
- No infinite loops — all loops have a clear exit condition

---

## Submission

Submit `loops-app.html`.
