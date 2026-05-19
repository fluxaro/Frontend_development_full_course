# Assignment — Type Conversion Utility

## What You Are Building

A set of utility functions that safely convert between types, plus a demonstration page showing coercion traps.

---

## Requirements

Create `type-conversion.html` with:

### Utility Functions
- [ ] `toSafeNumber(value)` — converts to number, returns 0 if NaN
- [ ] `toSafeString(value)` — converts any value to a readable string
- [ ] `toBoolean(value)` — explicit boolean conversion with explanation
- [ ] `parsePrice(str)` — parses a price string like '$29.99' to a number

### Coercion Trap Demonstrations
- [ ] Show 5 examples where `+` causes unexpected string concatenation
- [ ] Show 5 examples where `==` gives surprising results
- [ ] Show the same 5 examples with `===` giving expected results

### Interactive Converter
- [ ] Input field for a value
- [ ] Buttons to convert to Number, String, Boolean
- [ ] Display the result and the typeof the result

---

## Submission

Submit `type-conversion.html`.
