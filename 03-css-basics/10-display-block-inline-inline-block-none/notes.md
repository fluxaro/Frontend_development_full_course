# Notes — Display Property

## Quick Reference

| Value | Width | New Line | Width/Height |
|---|---|---|---|
| `block` | Full | Yes | Yes |
| `inline` | Content | No | No |
| `inline-block` | Content | No | Yes |
| `none` | 0 | — | — |
| `flex` | Full | Yes | Yes |
| `grid` | Full | Yes | Yes |

## display: none vs visibility: hidden

```css
.hidden { display: none; }       /* removed from layout, no space */
.invisible { visibility: hidden; } /* invisible but keeps space */
```

## Common Patterns

```css
/* Horizontal nav */
nav li { display: inline-block; }

/* Full-width nav links */
nav a { display: block; }

/* Badge/tag */
.badge { display: inline-block; padding: 2px 8px; }

/* Hide/show */
.modal { display: none; }
.modal.open { display: flex; }
```

## Common Mistakes

- Setting `width` on `display: inline` (has no effect)
- Forgetting that `display: none` removes from accessibility tree
- Using `visibility: hidden` when you want to remove space
- Not knowing that `<img>` is `inline` by default (causes bottom gap)
