# Assignment — Specificity Debugging Exercise

## What You Are Building

A page that demonstrates specificity conflicts and how to resolve them without `!important`.

---

## Part 1: Identify the Winner

For each CSS rule set below, predict which color the element will be and explain why:

```css
/* Rule A */ p { color: blue; }
/* Rule B */ .text { color: red; }
/* Rule C */ p.text { color: green; }
/* Rule D */ #main p { color: purple; }
```

```html
<div id="main">
  <p class="text">What color am I?</p>
</div>
```

Write your answer and explanation in a `specificity-answers.md` file.

---

## Part 2: Fix Without !important

Create `specificity-fix.html` and `specificity-fix.css`. The HTML has these elements:

```html
<nav class="main-nav">
  <a href="/" class="nav-link active">Home</a>
  <a href="/about" class="nav-link">About</a>
</nav>

<article class="post">
  <h2 class="post-title">Article Title</h2>
  <p class="post-text">Article content...</p>
  <p class="post-text highlight">Highlighted content...</p>
</article>
```

Write CSS that:
1. Makes all `.nav-link` elements white
2. Makes the `.active` nav link yellow — WITHOUT using `!important`
3. Makes all `.post-text` gray
4. Makes `.post-text.highlight` dark blue — WITHOUT using `!important`
5. Makes `h2.post-title` inside `.post` larger than regular h2 elements

---

## Part 3: Inheritance Demo

Create a section that demonstrates inheritance:
- Set `font-family` on `body` and show it inherits to all children
- Set `color` on a parent div and show children inherit it
- Show that `border` does NOT inherit
- Use `inherit` keyword to force a non-inherited property to inherit

---

## Submission

Submit `specificity-answers.md`, `specificity-fix.html`, and `specificity-fix.css`.
