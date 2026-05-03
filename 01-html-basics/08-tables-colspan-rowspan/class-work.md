# Class Work — Build a Class Schedule Table

## What You Will Build

A weekly class schedule table that uses colspan to merge cells for lunch breaks and rowspan to merge cells for multi-hour classes.

**Time:** 40 minutes

---

## Step 1 — Set Up the Page

Create a file called `class-schedule.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Weekly Class Schedule</title>
  </head>
  <body>
    <h1>Weekly Class Schedule</h1>
  </body>
</html>
```

---

## Step 2 — Build the Basic Table Structure

```html
<table border="1">
  <caption>Frontend Bootcamp — Week 1 Schedule</caption>
  <thead>
    <tr>
      <th scope="col">Time</th>
      <th scope="col">Monday</th>
      <th scope="col">Tuesday</th>
      <th scope="col">Wednesday</th>
      <th scope="col">Thursday</th>
      <th scope="col">Friday</th>
    </tr>
  </thead>
  <tbody>

  </tbody>
</table>
```

---

## Step 3 — Add Morning Rows

Inside `<tbody>`, add the morning schedule:

```html
<tr>
  <th scope="row">9:00 AM</th>
  <td>HTML Basics</td>
  <td>CSS Fundamentals</td>
  <td>JavaScript Intro</td>
  <td>React Basics</td>
  <td>Project Work</td>
</tr>
<tr>
  <th scope="row">10:00 AM</th>
  <td>HTML Practice</td>
  <td>CSS Practice</td>
  <td>JS Practice</td>
  <td>React Practice</td>
  <td>Project Work</td>
</tr>
<tr>
  <th scope="row">11:00 AM</th>
  <td>Code Review</td>
  <td>Code Review</td>
  <td>Code Review</td>
  <td>Code Review</td>
  <td>Code Review</td>
</tr>
```

---

## Step 4 — Add Lunch Break with colspan

The lunch break spans all 5 days — use `colspan="5"`:

```html
<tr>
  <th scope="row">12:00 PM</th>
  <td colspan="5">Lunch Break</td>
</tr>
```

**What happens:** Instead of 5 separate `<td>` cells, one cell spans all 5 columns. The total is still 6 cells (1 time + 5 days = 6), but we write it as 2 cells (1 time + 1 spanning cell).

---

## Step 5 — Add Afternoon Rows

```html
<tr>
  <th scope="row">1:00 PM</th>
  <td>Assignment</td>
  <td>Assignment</td>
  <td>Assignment</td>
  <td>Assignment</td>
  <td>Presentations</td>
</tr>
<tr>
  <th scope="row">2:00 PM</th>
  <td>Q&amp;A Session</td>
  <td>Q&amp;A Session</td>
  <td>Q&amp;A Session</td>
  <td>Q&amp;A Session</td>
  <td>Presentations</td>
</tr>
```

---

## Step 6 — Add a Row with rowspan

Now add a "Workshop" that runs from 3:00 PM to 4:00 PM on Wednesday only. Use `rowspan="2"` to span two rows:

```html
<tr>
  <th scope="row">3:00 PM</th>
  <td>Free Study</td>
  <td>Free Study</td>
  <td rowspan="2">Full Workshop</td>
  <td>Free Study</td>
  <td>Free Study</td>
</tr>
<tr>
  <th scope="row">4:00 PM</th>
  <td>Free Study</td>
  <td>Free Study</td>
  <!-- No td here for Wednesday — rowspan covers it -->
  <td>Free Study</td>
  <td>Free Study</td>
</tr>
```

**What happens:** The Wednesday cell from 3:00 PM spans down into the 4:00 PM row. So the 4:00 PM row only has 5 `<td>` cells instead of 6 (the Wednesday slot is already occupied by the rowspan).

---

## Step 7 — Add a Footer

```html
<tfoot>
  <tr>
    <td colspan="6">Total: 35 hours per week | Location: Online via Zoom</td>
  </tr>
</tfoot>
```

---

## Checklist

- [ ] Table has `<caption>`
- [ ] `<thead>`, `<tbody>`, `<tfoot>` are all present
- [ ] All `<th>` elements have `scope` attribute
- [ ] `colspan="5"` used for lunch break
- [ ] `rowspan="2"` used for the workshop
- [ ] Row with rowspan has the correct number of `<td>` elements
- [ ] Page opens in browser with no errors

---

## Bonus Challenges

1. Add a second table showing a comparison of programming languages
2. Add `colspan` to create a "Q1 / Q2 / Q3 / Q4" header that spans multiple months
3. Add `rowspan` to create a "Weekend" row header that spans Saturday and Sunday
4. Add a `<colgroup>` to style specific columns
