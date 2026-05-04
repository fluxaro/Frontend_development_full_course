# 33 — BEM Methodology

## What Is This Lesson About?

BEM (Block, Element, Modifier) is a CSS naming convention that makes your class names self-documenting and prevents specificity conflicts. It is widely used in professional frontend development.

---

## BEM Structure

```
Block__Element--Modifier
```

- **Block** — A standalone component: `.card`, `.nav`, `.btn`
- **Element** — A part of a block: `.card__title`, `.nav__link`
- **Modifier** — A variant or state: `.card--featured`, `.btn--primary`

---

## Example

```html
<nav class="nav">
  <span class="nav__logo">Brand</span>
  <ul class="nav__list">
    <li class="nav__item">
      <a class="nav__link" href="#">Home</a>
    </li>
    <li class="nav__item nav__item--active">
      <a class="nav__link nav__link--active" href="#">About</a>
    </li>
  </ul>
</nav>
```

```css
.nav { background: #2c3e50; }
.nav__logo { color: white; font-weight: bold; }
.nav__list { list-style: none; display: flex; }
.nav__item { }
.nav__item--active { }
.nav__link { color: #bdc3c7; text-decoration: none; }
.nav__link--active { color: white; font-weight: 600; }
```

---

## Benefits

1. **Self-documenting** — You can tell what an element does from its class name
2. **No specificity wars** — All selectors have the same specificity (0,1,0)
3. **Reusable** — Blocks can be used anywhere without style conflicts
4. **Scalable** — Works well in large codebases and teams

---

## Rules

1. Elements belong to blocks: `.card__title` (not `.card__body__title`)
2. Never nest BEM selectors: `.card .card__title` is wrong
3. Modifiers extend, not replace: always use both `.btn` and `.btn--primary`
4. Blocks can contain other blocks
