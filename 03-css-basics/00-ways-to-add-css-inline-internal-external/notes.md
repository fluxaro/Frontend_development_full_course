# Notes — Ways to Add CSS

## Three Methods Summary

| Method | Syntax | Priority | Use When |
|---|---|---|---|
| Inline | `style="color: red"` | Highest | Quick test, JS-applied |
| Internal | `<style>` in `<head>` | Medium | Single page |
| External | `<link href="style.css">` | Normal | Always (real projects) |

## CSS Syntax

```css
selector {
  property: value;
}
```

## Linking External CSS

```html
<link rel="stylesheet" href="style.css">
<link rel="stylesheet" href="css/style.css">
<link rel="stylesheet" href="../style.css">
```

## Multiple Stylesheets

```html
<link rel="stylesheet" href="reset.css">
<link rel="stylesheet" href="style.css">
<link rel="stylesheet" href="components.css">
```

Later files override earlier ones for the same property.

## Common Mistakes

- Forgetting `rel="stylesheet"` on the link tag
- Wrong file path in `href`
- Putting `<style>` in `<body>` instead of `<head>`
- Using inline styles for everything (hard to maintain)
- Not separating CSS into its own file for multi-page sites

## CSS Comments

```css
/* This is a CSS comment */

/* 
  Multi-line
  comment
*/
```
