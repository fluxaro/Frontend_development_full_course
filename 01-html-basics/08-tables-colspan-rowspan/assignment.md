# Assignment — Smartphone Comparison Table

## What You Are Building

Create an HTML page called `phone-comparison.html` — a comparison table for 3 smartphones using colspan and rowspan.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### 1. Page Structure
- Proper `<!DOCTYPE html>`, `<html lang>`, `<head>`, `<body>`
- `<h1>` with the page title
- `<main>` wrapping the content

### 2. Main Comparison Table

The table must:
- Have a `<caption>` describing the table
- Have `<thead>`, `<tbody>`, and `<tfoot>`
- Use `scope` on all `<th>` elements
- Compare at least 3 smartphones
- Have at least 12 rows of specifications

**Required specifications to include:**
- Brand and Model (as column headers)
- Display Size
- Display Type
- Processor
- RAM
- Storage Options (use colspan to group storage variants)
- Main Camera
- Battery Capacity
- Operating System
- Price (Starting)
- Release Year

**Required colspan usage:**
- A top-level header row that spans all phone columns (e.g., "2025 Flagship Comparison")
- At least one cell that spans multiple columns

**Required rowspan usage:**
- At least one row header that spans multiple rows (e.g., "Camera System" spanning front and rear camera rows)

### 3. Footer Row
A `<tfoot>` row with a note about where the data came from.

---

## What Good Looks Like

- The table is accurate (real phone specs)
- colspan and rowspan numbers are correct (cells align properly)
- All `<th>` elements have `scope` attribute
- The table has a meaningful `<caption>`
- The page passes W3C validation

---

## Bonus Challenges

- Add a second table comparing the same phones' camera specs in detail
- Add a `<colgroup>` to visually group the phone columns
- Add a "Winner" row at the bottom using colspan
- Add a `<nav>` with anchor links if you have multiple tables

---

## Submission

Save as `phone-comparison.html` and submit via GitHub.
