# 27 — CSS Animations and @keyframes

## What Is This Lesson About?

CSS animations let you create complex, multi-step animations without JavaScript. Unlike transitions (which animate between two states), animations can have multiple steps and run automatically.

---

## @keyframes

Define the animation steps:

```css
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

@keyframes slideUp {
  from { transform: translateY(20px); opacity: 0; }
  to   { transform: translateY(0);    opacity: 1; }
}

@keyframes bounce {
  0%   { transform: translateY(0); }
  50%  { transform: translateY(-20px); }
  100% { transform: translateY(0); }
}
```

---

## animation Properties

```css
.element {
  animation-name: fadeIn;
  animation-duration: 0.5s;
  animation-timing-function: ease;
  animation-delay: 0.2s;
  animation-iteration-count: 1;      /* or infinite */
  animation-direction: normal;       /* or reverse, alternate */
  animation-fill-mode: forwards;     /* keep end state */
  animation-play-state: running;     /* or paused */
}

/* Shorthand */
animation: fadeIn 0.5s ease 0.2s 1 normal forwards;
```

---

## animation-fill-mode

```css
animation-fill-mode: none;      /* default: returns to original */
animation-fill-mode: forwards;  /* keeps end state */
animation-fill-mode: backwards; /* applies start state during delay */
animation-fill-mode: both;      /* both forwards and backwards */
```

---

## Multiple Animations

```css
animation: fadeIn 0.5s ease, slideUp 0.5s ease;
```

---

## Common Animations

```css
/* Fade in */
@keyframes fadeIn {
  from { opacity: 0; }
  to   { opacity: 1; }
}

/* Slide up */
@keyframes slideUp {
  from { transform: translateY(30px); opacity: 0; }
  to   { transform: translateY(0);    opacity: 1; }
}

/* Spin */
@keyframes spin {
  from { transform: rotate(0deg); }
  to   { transform: rotate(360deg); }
}

/* Pulse */
@keyframes pulse {
  0%, 100% { transform: scale(1); }
  50%       { transform: scale(1.05); }
}

/* Shake */
@keyframes shake {
  0%, 100% { transform: translateX(0); }
  25%       { transform: translateX(-8px); }
  75%       { transform: translateX(8px); }
}
```
