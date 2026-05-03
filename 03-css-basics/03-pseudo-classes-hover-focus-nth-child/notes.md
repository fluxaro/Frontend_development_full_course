# Notes — Pseudo-classes

## Quick Reference

```css
/* User actions */
:hover      /* mouse over */
:focus      /* keyboard focus */
:active     /* being clicked */
:visited    /* visited link */

/* Form states */
:checked    /* checked checkbox/radio */
:disabled   /* disabled input */
:enabled    /* enabled input */
:required   /* required field */
:valid      /* valid input */
:invalid    /* invalid input */

/* Structural */
:first-child        /* first child */
:last-child         /* last child */
:nth-child(n)       /* nth child */
:nth-child(even)    /* even children */
:nth-child(odd)     /* odd children */
:nth-of-type(n)     /* nth of same type */
:only-child         /* only child */
:not(selector)      /* not matching */
:empty              /* no children */
:root               /* html element */
```

## nth-child Formulas

| Formula | Selects |
|---|---|
| `nth-child(2)` | 2nd child |
| `nth-child(even)` | 2nd, 4th, 6th... |
| `nth-child(odd)` | 1st, 3rd, 5th... |
| `nth-child(3n)` | 3rd, 6th, 9th... |
| `nth-child(3n+1)` | 1st, 4th, 7th... |
| `nth-child(-n+3)` | 1st, 2nd, 3rd |
| `nth-child(n+4)` | 4th onwards |

## Common Patterns

```css
/* Zebra striping */
tr:nth-child(even) { background: #f5f5f5; }

/* Remove last border */
li:not(:last-child) { border-bottom: 1px solid #eee; }

/* Style first paragraph differently */
p:first-of-type { font-size: 1.2rem; font-weight: 500; }

/* Focus styles */
:focus-visible { outline: 2px solid #3498db; outline-offset: 2px; }
```

## Common Mistakes

- Removing focus styles (accessibility failure)
- Using `:hover` without `:focus` (keyboard users miss the style)
- Wrong LVHA order for links
- Using `:nth-child` when you need `:nth-of-type`
