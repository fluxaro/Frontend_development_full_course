# Notes — Tables, colspan, rowspan

## Table Structure Cheat Sheet

```html
<table>
  <caption>Table Title</caption>
  <thead>
    <tr>
      <th scope="col">Column 1</th>
      <th scope="col">Column 2</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>Data</td>
      <td>Data</td>
    </tr>
  </tbody>
  <tfoot>
    <tr>
      <td>Total</td>
      <td>Value</td>
    </tr>
  </tfoot>
</table>
```

## colspan and rowspan

```html
<!-- Span 3 columns -->
<td colspan="3">This cell spans 3 columns</td>

<!-- Span 2 rows -->
<td rowspan="2">This cell spans 2 rows</td>
```

**Rule:** When you use `rowspan="2"`, the next row must have one fewer `<td>` because the spanned cell takes up that space.

## scope Attribute

```html
<th scope="col">Column header</th>
<th scope="row">Row header</th>
<th scope="colgroup">Header for a group of columns</th>
<th scope="rowgroup">Header for a group of rows</th>
```

## All Table Elements

| Element | Purpose |
|---|---|
| `<table>` | Container |
| `<caption>` | Title/description |
| `<thead>` | Header section |
| `<tbody>` | Body section |
| `<tfoot>` | Footer section |
| `<tr>` | Row |
| `<th>` | Header cell |
| `<td>` | Data cell |
| `<colgroup>` | Group of columns |
| `<col>` | Individual column |

## Common Mistakes

- Using tables for layout (use CSS Grid/Flexbox instead)
- Forgetting `<caption>` (accessibility)
- Forgetting `scope` on `<th>` (accessibility)
- Wrong colspan/rowspan numbers (cells won't align)
- Putting `<tr>` directly in `<table>` without `<tbody>` (works but not best practice)

## colspan/rowspan Math

If a row has 3 columns and one cell has `colspan="2"`, that row only needs 2 `<td>` elements (2 + 1 = 3 total columns).

If a cell has `rowspan="3"`, the next 2 rows each need one fewer `<td>`.
