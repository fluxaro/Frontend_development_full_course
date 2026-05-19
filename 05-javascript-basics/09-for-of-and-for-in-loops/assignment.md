# Assignment — Data Explorer

## What You Are Building

An interactive data explorer that uses `for-of` and `for-in` to process and display a dataset of students, demonstrating when to use each loop type.

---

## Requirements

Create `data-explorer.html` with this dataset already defined:

```javascript
const students = [
  { name: 'Alex Rivera', grade: 92, subject: 'JavaScript', city: 'Lagos' },
  { name: 'Sam Okafor', grade: 78, subject: 'CSS', city: 'Abuja' },
  { name: 'Jordan Lee', grade: 85, subject: 'React', city: 'Lagos' },
  { name: 'Morgan Kim', grade: 61, subject: 'HTML', city: 'Port Harcourt' },
  { name: 'Taylor Chen', grade: 95, subject: 'JavaScript', city: 'Lagos' },
  { name: 'Casey Brown', grade: 73, subject: 'CSS', city: 'Abuja' },
];
```

### Part 1 — Student List (for-of)

- Use `for-of` to loop through the students array
- Display each student as a card showing: name, grade, subject, city
- Colour-code the grade: green (≥80), yellow (60–79), red (<60)

### Part 2 — Object Inspector (for-in)

- Pick any one student object
- Use `for-in` to loop through all its properties
- Display a table showing: Property | Value | Type (using `typeof`)

### Part 3 — Statistics (for-of with accumulation)

Use `for-of` to calculate and display:
- Total number of students
- Average grade (rounded to 1 decimal)
- Highest grade and the student who achieved it
- Lowest grade and the student who achieved it
- Number of students who passed (grade ≥ 60)

### Part 4 — Group by City (for-of with object building)

- Use `for-of` to group students by city
- Display each city as a section with its students listed underneath

### Part 5 — for-of vs forEach Comparison

- Show the same operation (listing student names) done with both `for-of` and `forEach`
- Add a comment explaining when you'd choose one over the other

---

## What Good Looks Like

- Student cards are styled and readable
- Statistics are accurate
- City grouping is correct
- Code uses `for-of` and `for-in` appropriately (not `for` loops where `for-of` is cleaner)

---

## Submission

Submit `data-explorer.html`.
