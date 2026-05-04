# 10 — Display: block, inline, inline-block, none

## What Is This Lesson About?

The `display` property controls how an element participates in the layout. It is one of the most important CSS properties — it determines whether an element takes up a full line, sits inline with text, or is hidden entirely.

---

## display: block

Block elements take up the full width available and start on a new line.

```css
div, p, h1, h2, section, article, header, footer { display: block; }
```

- Takes up full width of parent
- Starts on a new line
- Can have width, height, margin, padding on all sides
- Examples: `<div>`, `<p>`, `<h1>`, `<section>`

---

## display: inline

Inline elements sit within the flow of text. They only take up as much width as their content.

```css
span, a, strong, em, code { display: inline; }
```

- Only as wide as content
- Does NOT start on a new line
- Width and height have NO effect
- Top/bottom margin and padding have limited effect
- Examples: `<span>`, `<a>`, `<strong>`, `<em>`

---

## display: inline-block

Combines inline and block behavior.

```css
.badge { display: inline-block; }
```

- Sits inline with text (like inline)
- Can have width, height, margin, padding (like block)
- Examples: `<img>`, `<button>`, `<input>`

---

## display: none

Completely removes the element from the layout. It takes up no space.

```css
.hidden { display: none; }
```

Different from `visibility: hidden` which hides the element but keeps its space.

---

## display: flex and grid

Modern layout values — covered in their own lessons.

```css
.container { display: flex; }
.grid { display: grid; }
```

---

## Comparison Table

| Property | Takes Full Width | New Line | Width/Height | Inline with Text |
|---|---|---|---|---|
| `block` | Yes | Yes | Yes | No |
| `inline` | No | No | No | Yes |
| `inline-block` | No | No | Yes | Yes |
| `none` | — | — | — | — |

---

## Common Use Cases

```css
/* Make links block for full-width click area */
nav a { display: block; padding: 12px 20px; }

/* Make list items horizontal */
nav li { display: inline-block; }

/* Hide on mobile, show on desktop */
.desktop-only { display: none; }
@media (min-width: 768px) {
  .desktop-only { display: block; }
}

/* Inline badge */
.badge {
  display: inline-block;
  padding: 2px 8px;
  border-radius: 12px;
  font-size: 0.75rem;
}
```
