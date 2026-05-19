# Assignment — Grade Calculator and Day Classifier

## What You Are Building

An interactive web app with two tools: a grade calculator that uses `if/else` and a day classifier that uses `switch`. Both tools respond to user input in real time.

---

## Requirements

Create `control-flow-app.html` with:

### Part 1 — Grade Calculator

Build a form with:
- A number input for a score (0–100)
- A "Calculate" button
- A result area that shows:
  - The letter grade (A, B, C, D, F)
  - A message ("Excellent!", "Good job!", "Satisfactory", "Needs improvement", "Please retake")
  - The result box changes background colour based on the grade (green for A, blue for B, yellow for C, orange for D, red for F)

Use `if / else if / else` for the grade logic:
- 90–100 → A
- 80–89 → B
- 70–79 → C
- 60–69 → D
- 0–59 → F

### Part 2 — Day Classifier

Build a form with:
- A text input for a day name
- A "Classify" button
- A result showing "Weekday", "Weekend", or "Invalid day"
- Use `switch` for the logic
- Make it case-insensitive (convert to lowercase before switching)

### Part 3 — Traffic Light

Build a traffic light simulator:
- Three buttons: Red, Yellow, Green
- When clicked, display the action for that light:
  - Red → "STOP — Do not proceed"
  - Yellow → "CAUTION — Prepare to stop or go carefully"
  - Green → "GO — Proceed safely"
- Style the result text with the matching colour
- Use `switch` for the logic

### Part 4 — Season Finder

Build a form with:
- A number input for a month (1–12)
- A "Find Season" button
- Display the season (Spring, Summer, Autumn, Winter)
- Use `switch` with fall-through for months that share a season

---

## What Good Looks Like

- All four tools work correctly with valid and invalid inputs
- Invalid inputs show a helpful error message (e.g., score outside 0–100)
- The UI is styled — not plain HTML
- No errors in the browser console

---

## Submission

Submit `control-flow-app.html`.
