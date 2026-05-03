# Notes — Cascade, Specificity, Inheritance

## Specificity Cheat Sheet

| Selector | Score |
|---|---|
| `*` | 0 |
| `p`, `div`, `h1` | 1 |
| `.class`, `[attr]`, `:hover` | 10 |
| `#id` | 100 |
| `style=""` | 1000 |
| `!important` | Wins everything |

## Calculating Specificity

```
p.card#header a:hover
= 0 IDs + 2 classes + 2 elements
= 0,2,2 = 22 points
```

## Cascade Order (lowest to highest)

1. Browser default styles
2. External stylesheets
3. Internal `<style>` block
4. Inline `style=""` attribute
5. `!important`

## Inheritance Keywords

```css
color: inherit;   /* use parent's value */
color: initial;   /* use browser default */
color: unset;     /* inherit if inheritable, else initial */
color: revert;    /* revert to browser stylesheet */
```

## Inherited vs Not Inherited

| Inherited | Not Inherited |
|---|---|
| color | margin |
| font-family | padding |
| font-size | border |
| line-height | background |
| text-align | width/height |
| list-style | display |

## Common Mistakes

- Using `!important` everywhere (creates specificity wars)
- Overly specific selectors (`div.container > ul > li > a`)
- Not understanding why a style is not applying (check specificity)
- Forgetting that some properties do not inherit
