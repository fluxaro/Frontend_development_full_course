# 08 — Tables, colspan, and rowspan

## What Is This Lesson About?

HTML tables are for displaying tabular data — information that naturally fits in rows and columns. This lesson covers how to build tables correctly, how to span cells across multiple columns or rows, and when tables are appropriate.

---

## Basic Table Structure

```html
<table>
  <caption>Monthly Sales Report</caption>
  <thead>
    <tr>
      <th scope="col">Month</th>
      <th scope="col">Sales</th>
      <th scope="col">Revenue</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>January</td>
      <td>120</td>
      <td>$12,000</td>
    </tr>
    <tr>
      <td>February</td>
      <td>145</td>
      <td>$14,500</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>265</td>
      <td>$26,500</td>
    </tr>
  </tfoot>
</table>
```

### Table Elements

| Element | Purpose |
|---|---|
| `<table>` | The table container |
| `<caption>` | Title/description of the table |
| `<thead>` | Header rows group |
| `<tbody>` | Body rows group |
| `<tfoot>` | Footer rows group |
| `<tr>` | Table row |
| `<th>` | Table header cell (bold, centered by default) |
| `<td>` | Table data cell |

---

## colspan — Span Across Columns

`colspan` makes a cell span multiple columns horizontally:

```html
<table>
  <thead>
    <tr>
      <th colspan="3">Q1 Sales Report</th>  <!-- spans 3 columns -->
    </tr>
    <tr>
      <th>January</th>
      <th>February</th>
      <th>March</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>$10,000</td>
      <td>$12,000</td>
      <td>$11,500</td>
    </tr>
  </tbody>
</table>
```

---

## rowspan — Span Across Rows

`rowspan` makes a cell span multiple rows vertically:

```html
<table>
  <tbody>
    <tr>
      <td rowspan="2">Monday</td>  <!-- spans 2 rows -->
      <td>9:00 AM</td>
      <td>Math</td>
    </tr>
    <tr>
      <!-- No first cell here — Monday spans this row too -->
      <td>10:00 AM</td>
      <td>English</td>
    </tr>
  </tbody>
</table>
```

---

## The `scope` Attribute for Accessibility

The `scope` attribute on `<th>` tells screen readers whether the header applies to a column or a row:

```html
<thead>
  <tr>
    <th scope="col">Name</th>
    <th scope="col">Age</th>
    <th scope="col">City</th>
  </tr>
</thead>
<tbody>
  <tr>
    <th scope="row">Alice</th>  <!-- row header -->
    <td>28</td>
    <td>New York</td>
  </tr>
</tbody>
```

---

## When to Use Tables

**Use tables for:**
- Data that has rows and columns (spreadsheet-like data)
- Comparison tables
- Schedules and timetables
- Financial reports
- Sports standings

**Do NOT use tables for:**
- Page layout (use CSS Flexbox or Grid instead)
- Navigation menus
- Anything that is not genuinely tabular data

---

## Common Mistakes

- Using tables for layout (this was done in the 1990s — never do it now)
- Missing `<thead>`, `<tbody>`, `<tfoot>` (they are optional but best practice)
- Missing `<caption>` (important for accessibility)
- Missing `scope` on `<th>` elements
- Incorrect colspan/rowspan counts (the numbers must add up correctly)
