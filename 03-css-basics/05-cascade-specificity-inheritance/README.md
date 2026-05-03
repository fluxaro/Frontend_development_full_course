# 05 — The Cascade, Specificity, and Inheritance

## What Is This Lesson About?

The "C" in CSS stands for Cascading. Understanding how the cascade, specificity, and inheritance work is essential — it explains why your styles sometimes don't apply and how to fix it without resorting to `!important`.

---

## The Cascade

When multiple CSS rules target the same element and property, the cascade determines which one wins. It considers three factors in order:

1. **Origin** — where the style comes from (browser, user, author)
2. **Specificity** — how specific the selector is
3. **Order** — which rule appears last in the code

---

## Specificity

Specificity is a score that determines which rule wins when multiple rules target the same element. Think of it as a 4-digit number: `(inline, IDs, classes, elements)`.

| Selector | Specificity |
|---|---|
| `*` | 0,0,0,0 |
| `p`, `div`, `h1` | 0,0,0,1 |
| `.class`, `:hover`, `[attr]` | 0,0,1,0 |
| `#id` | 0,1,0,0 |
| `style=""` (inline) | 1,0,0,0 |
| `!important` | Overrides everything |

### Calculating Specificity

```css
p                    /* 0,0,0,1 */
.card                /* 0,0,1,0 */
#header              /* 0,1,0,0 */
.card p              /* 0,0,1,1 */
#header .nav a       /* 0,1,1,1 */
.card.featured       /* 0,0,2,0 */
```

The higher number wins. If equal, the **last rule** in the stylesheet wins.

---

## Inheritance

Some CSS properties are inherited by child elements. Others are not.

### Inherited Properties (pass down to children)

```
color, font-family, font-size, font-weight, font-style,
line-height, letter-spacing, text-align, text-transform,
visibility, cursor, list-style
```

### Non-inherited Properties (do NOT pass down)

```
margin, padding, border, background, width, height,
display, position, top, left, right, bottom,
box-shadow, transform, opacity, overflow
```

### Forcing Inheritance

```css
/* Force a property to inherit */
.child {
  border: inherit;
  background: inherit;
}

/* Reset to initial value */
.child {
  color: initial;
}

/* Use the inherited value */
.child {
  color: inherit;
}

/* Revert to browser default */
.child {
  color: revert;
}
```

---

## !important

`!important` overrides all specificity rules. Use it as a last resort only.

```css
.button {
  color: blue !important;  /* wins over everything */
}
```

**When to use `!important`:**
- Overriding third-party library styles
- Utility classes that must always apply
- Never in your own component styles

---

## Practical Tips

```css
/* Instead of !important, increase specificity */
/* Bad */
.card p { color: red !important; }

/* Good */
.card.featured p { color: red; }

/* Or use a more specific selector */
article.card p { color: red; }
```

---

## The `all` Property

Reset all properties at once:

```css
.reset {
  all: initial;    /* reset to browser defaults */
  all: inherit;    /* inherit everything */
  all: unset;      /* inherit if inheritable, else initial */
  all: revert;     /* revert to browser stylesheet */
}
```
