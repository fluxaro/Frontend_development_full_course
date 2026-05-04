# 31 — Cascade Layers (@layer)

## What Is This Lesson About?

Cascade layers let you explicitly control the order in which CSS rules are applied — without fighting specificity. They are the solution to the "specificity wars" problem in large codebases.

---

## The Problem

In large projects, CSS from different sources (resets, frameworks, components, utilities) can conflict. The only way to override was to increase specificity or use `!important`.

---

## @layer

```css
/* Define layer order */
@layer reset, base, components, utilities;

/* Later layers win over earlier layers */
/* utilities > components > base > reset */
```

---

## Defining Layers

```css
/* Inline layer */
@layer reset {
  * { box-sizing: border-box; }
}

/* Import into layer */
@import url('bootstrap.css') layer(framework);

/* Anonymous layer */
@layer {
  /* styles */
}
```

---

## Layer Priority

```css
@layer A, B, C;

/* C wins over B, B wins over A */
/* Even if A has higher specificity */

@layer A {
  .card { color: red; }  /* specificity: 0,1,0 */
}

@layer C {
  p { color: blue; }  /* specificity: 0,0,1 — but C wins! */
}
```

---

## Unlayered Styles

Styles outside any layer have the highest priority (above all layers):

```css
@layer base { .card { color: red; } }

/* This wins — it's outside any layer */
.card { color: blue; }
```

---

## Real-World Pattern

```css
/* Define order: reset < base < components < utilities */
@layer reset, base, components, utilities;

@layer reset {
  *, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
}

@layer base {
  body { font-family: sans-serif; color: #333; }
}

@layer components {
  .btn { background: #3498db; color: white; padding: 10px 20px; }
}

@layer utilities {
  .bg-red { background: red; }  /* always wins over components */
}
```
