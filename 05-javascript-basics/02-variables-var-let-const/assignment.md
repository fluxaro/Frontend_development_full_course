# Assignment — Variable Scope Explorer

## What You Are Building

A JavaScript program that demonstrates the difference between `var`, `let`, and `const` through practical examples. You will also build a simple profile object using proper variable declarations.

---

## Requirements

Create `variables-demo.html` with embedded JavaScript that:

### Part 1 — Scope Demonstration
- [ ] Show that `var` leaks out of an `if` block (log the variable both inside and outside)
- [ ] Show that `let` is block-scoped (log inside the block, then try outside — catch the error)
- [ ] Show that `const` cannot be reassigned (use a try/catch to catch the TypeError)

### Part 2 — Hoisting
- [ ] Demonstrate `var` hoisting: log a `var` variable before it is declared
- [ ] Show that `let` is in the Temporal Dead Zone: use a try/catch to show the ReferenceError

### Part 3 — User Profile
Create a `const` object called `userProfile` with:
- `name` (string)
- `age` (number)
- `skills` (array of at least 3 strings)
- `isEmployed` (boolean)

Then:
- [ ] Log the full object with `console.log`
- [ ] Log it with `console.table`
- [ ] Mutate the `age` property and log it again
- [ ] Push a new skill to the `skills` array and log it

### Part 4 — Naming Practice
- [ ] Declare 3 variables with good camelCase names
- [ ] Declare 2 constants with SCREAMING_SNAKE_CASE names
- [ ] Add a comment explaining why each uses `const` or `let`

---

## What Good Looks Like

- Console output is organised with labels
- Scope differences are clearly demonstrated
- The profile object is realistic and well-named
- All variables use `const` unless reassignment is needed

---

## Submission

Submit `variables-demo.html`.
