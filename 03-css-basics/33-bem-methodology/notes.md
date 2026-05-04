# Notes — BEM Methodology

## BEM Naming Convention

```
Block__Element--Modifier

.block { }
.block__element { }
.block__element--modifier { }
.block--modifier { }
```

## Examples

```html
<div class="card card--featured">
  <img class="card__image" src="...">
  <div class="card__body">
    <h2 class="card__title">Title</h2>
    <p class="card__text">Text</p>
    <button class="card__btn card__btn--primary">Action</button>
  </div>
</div>
```

```css
.card { }
.card--featured { }
.card__image { }
.card__body { }
.card__title { }
.card__text { }
.card__btn { }
.card__btn--primary { }
```

## Rules

- Block: standalone component (`.card`, `.nav`, `.btn`)
- Element: part of a block (`.card__title`, `.nav__link`)
- Modifier: variant or state (`.card--featured`, `.btn--primary`)
- Never nest BEM classes (`.card .card__title` is wrong)
- Elements belong to blocks, not other elements

## Common Mistakes

- `.card__body__title` — elements cannot have elements
- `.card .card__title` — do not nest BEM selectors
- Using modifiers without the base class
- Mixing BEM with other naming conventions
