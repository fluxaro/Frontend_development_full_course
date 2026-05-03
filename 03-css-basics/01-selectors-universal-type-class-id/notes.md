# Notes — CSS Selectors

## Selector Cheat Sheet

```css
/* Universal — all elements */
* { box-sizing: border-box; }

/* Type — all h1 elements */
h1 { color: blue; }

/* Class — all elements with class="card" */
.card { border: 1px solid #ddd; }

/* ID — the element with id="header" */
#header { background: #333; }

/* Multiple classes on one element */
<div class="card featured large">

/* Grouping — apply same styles to multiple selectors */
h1, h2, h3 { font-family: serif; }
```

## Specificity Values

| Selector | Specificity |
|---|---|
| `*` | 0,0,0 |
| `p`, `div`, `h1` | 0,0,1 |
| `.class` | 0,1,0 |
| `#id` | 1,0,0 |
| `style=""` | 1,0,0,0 |

## Class vs ID

| | Class | ID |
|---|---|---|
| Syntax | `.name` | `#name` |
| Reusable | Yes | No |
| Per element | Multiple | One |
| Specificity | 10 | 100 |

## Common Mistakes

- Using `#id` for styling (use `.class` instead — IDs are for JS and anchors)
- Forgetting the `.` before class names in CSS
- Forgetting the `#` before ID names in CSS
- Using the same ID on multiple elements (IDs must be unique)
- Over-qualifying selectors: `p.text` when `.text` is enough
