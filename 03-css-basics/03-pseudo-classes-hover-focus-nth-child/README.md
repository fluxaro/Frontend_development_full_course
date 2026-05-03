# 03 — Pseudo-classes: :hover, :focus, :nth-child, and More

## What Is This Lesson About?

Pseudo-classes let you style elements based on their state or position — without adding extra classes to your HTML. They are one of the most powerful features in CSS.

---

## What Is a Pseudo-class?

A pseudo-class is a keyword added to a selector that specifies a special state of the selected element.

```css
selector:pseudo-class {
  property: value;
}
```

---

## User Action Pseudo-classes

### :hover

Applies when the user moves their mouse over an element.

```css
a:hover {
  color: #e74c3c;
  text-decoration: underline;
}

.btn:hover {
  background-color: #2980b9;
  transform: translateY(-2px);
}
```

### :focus

Applies when an element receives keyboard focus (Tab key or click).

```css
input:focus {
  outline: 2px solid #3498db;
  border-color: #3498db;
}

button:focus {
  outline: 3px solid #f39c12;
  outline-offset: 2px;
}
```

**Never remove focus styles** — they are critical for keyboard accessibility.

### :active

Applies while an element is being clicked.

```css
button:active {
  transform: translateY(1px);
  box-shadow: none;
}
```

### :visited

Applies to links that have been visited.

```css
a:visited {
  color: #8e44ad;
}
```

---

## Form State Pseudo-classes

```css
input:disabled { opacity: 0.5; cursor: not-allowed; }
input:enabled { cursor: text; }
input:checked { accent-color: #3498db; }
input:required { border-left: 3px solid orange; }
input:valid { border-color: green; }
input:invalid { border-color: red; }
input:placeholder-shown { border-color: #ccc; }
input:focus-within { } /* parent when child is focused */
```

---

## Structural Pseudo-classes

### :first-child and :last-child

```css
li:first-child { font-weight: bold; }
li:last-child { border-bottom: none; }
```

### :nth-child()

```css
/* Every even row */
tr:nth-child(even) { background-color: #f5f5f5; }

/* Every odd row */
tr:nth-child(odd) { background-color: white; }

/* Every 3rd element */
li:nth-child(3n) { color: red; }

/* First 3 elements */
li:nth-child(-n+3) { font-weight: bold; }

/* From 4th onwards */
li:nth-child(n+4) { color: gray; }
```

### :nth-of-type()

Like `:nth-child()` but counts only elements of the same type.

```css
p:nth-of-type(2) { font-size: 1.2rem; }
```

### :only-child and :only-of-type

```css
li:only-child { list-style: none; }
p:only-of-type { font-size: 1.2rem; }
```

### :not()

Selects elements that do NOT match the selector.

```css
/* All buttons except disabled ones */
button:not(:disabled) { cursor: pointer; }

/* All list items except the last */
li:not(:last-child) { border-bottom: 1px solid #eee; }
```

### :empty

Selects elements with no children.

```css
p:empty { display: none; }
```

---

## Link Pseudo-classes (LVHA Order)

Always write link pseudo-classes in this order:

```css
a:link    { color: blue; }      /* Unvisited */
a:visited { color: purple; }   /* Visited */
a:hover   { color: red; }      /* Hovered */
a:active  { color: orange; }   /* Being clicked */
```

Remember: **L**o**V**e **HA**te (LVHA)
