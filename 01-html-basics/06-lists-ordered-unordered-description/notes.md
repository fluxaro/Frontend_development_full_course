# Notes — Lists: Ordered, Unordered, Description

## Quick Reference

### Unordered List
```html
<ul>
  <li>Item one</li>
  <li>Item two</li>
  <li>Item three</li>
</ul>
```
Use when: Order does not matter. Bullets by default.

### Ordered List
```html
<ol>
  <li>First step</li>
  <li>Second step</li>
  <li>Third step</li>
</ol>
```
Use when: Order matters. Numbers by default.

### Description List
```html
<dl>
  <dt>Term</dt>
  <dd>Definition of the term.</dd>

  <dt>Another term</dt>
  <dd>Its definition.</dd>
</dl>
```
Use when: Displaying term-value pairs, glossaries, FAQs.

### Nested List
```html
<ul>
  <li>Parent item
    <ul>
      <li>Child item</li>
      <li>Child item</li>
    </ul>
  </li>
</ul>
```

## Ordered List Attributes

| Attribute | Example | Effect |
|---|---|---|
| `start` | `<ol start="5">` | Start numbering from 5 |
| `reversed` | `<ol reversed>` | Count down (10, 9, 8...) |
| `type` | `<ol type="A">` | Use A, B, C instead of 1, 2, 3 |
| `type` | `<ol type="i">` | Use i, ii, iii (Roman numerals) |
| `type` | `<ol type="I">` | Use I, II, III (uppercase Roman) |

## When to Use Each

| Use Case | List Type |
|---|---|
| Navigation menu | `<ul>` |
| Ingredients | `<ul>` |
| Features list | `<ul>` |
| Step-by-step instructions | `<ol>` |
| Rankings | `<ol>` |
| Glossary | `<dl>` |
| FAQ | `<dl>` |
| Key-value metadata | `<dl>` |

## Common Mistakes

- Putting `<li>` directly inside `<dl>` (wrong — use `<dt>` and `<dd>`)
- Putting `<dt>` or `<dd>` inside `<ul>` or `<ol>` (wrong)
- Nesting a `<ul>` directly inside another `<ul>` without a `<li>` wrapper
- Using `<br>` to separate list items instead of separate `<li>` elements
- Using lists for layout instead of semantic content

## Valid Nesting

```html
<!-- CORRECT: ul inside li -->
<ul>
  <li>Parent
    <ul>
      <li>Child</li>
    </ul>
  </li>
</ul>

<!-- WRONG: ul directly inside ul -->
<ul>
  <ul>  <!-- Invalid! -->
    <li>Item</li>
  </ul>
</ul>
```
