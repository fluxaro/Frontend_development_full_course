# Assignment — Styled Component Library with Pseudo-elements

## What You Are Building

Create a component library page that uses `::before` and `::after` for all decorative elements.

---

## Requirements

Create `component-library.html` and `component-library.css` with these components, each using pseudo-elements:

### 1. Section Headings
- `::after` adds a colored underline bar
- `::before` adds a vertical accent bar on the left

### 2. Feature List
- `::before` adds custom checkmark bullets (✓)
- `::after` adds a subtle separator line between items

### 3. Testimonial Cards
- `::before` adds large opening quote mark
- `::after` adds large closing quote mark

### 4. Step-by-step Process
- `::before` adds numbered circles (use CSS counters)
- `::after` adds connecting lines between steps

### 5. Badge/Tag Component
- `::before` adds a colored dot indicator
- `::after` adds a small arrow/triangle on one side

### 6. Notification Banner
- `::before` adds an icon (⚠️ or ✓ or ℹ️)
- Different variants: success, warning, error, info

### 7. Tooltip on Any Element
- `::after` shows tooltip text from `data-tooltip` attribute
- Works on hover

---

## CSS Counter Requirement

Use CSS counters for the step-by-step process:

```css
.steps { counter-reset: step; }
.step::before {
  counter-increment: step;
  content: counter(step);
  /* style as a circle */
}
```

---

## What Good Looks Like

- No extra HTML elements for decoration
- All decorative content is in CSS `content` property
- Tooltips work on hover
- CSS counters are used correctly
- The page looks polished and professional

---

## Submission

Submit `component-library.html` and `component-library.css`.
