# Notes — Attribute Selectors

## Quick Reference

```css
[attr]        /* has attribute */
[attr="val"]  /* exact value */
[attr~="val"] /* contains word */
[attr^="val"] /* starts with */
[attr$="val"] /* ends with */
[attr*="val"] /* contains substring */
[attr|="val"] /* starts with val or val- */
[attr="val" i] /* case-insensitive */
```

## Common Patterns

```css
/* External links */
a[href^="http"]::after { content: ' ↗'; }

/* PDF links */
a[href$=".pdf"]::before { content: '📄 '; }

/* Required inputs */
input[required] { border-left: 3px solid orange; }

/* Disabled */
[disabled] { opacity: 0.5; cursor: not-allowed; }

/* Data attributes */
[data-theme="dark"] { background: #0f172a; }
```
