# Assignment — Card Component System

## What You Are Building

Create a complete card component system demonstrating mastery of the box model.

---

## Requirements

Create `card-system.html` and `card-system.css` with these card variants:

### Base Card
- `padding: 1.5rem`
- `border: 1px solid #e0e0e0`
- `border-radius: 8px`
- `margin-bottom: 1rem`

### Card Variants
1. **Default card** — white background
2. **Outlined card** — transparent background, colored border
3. **Elevated card** — white background, box-shadow, no border
4. **Colored card** — colored background, white text
5. **Horizontal card** — image on left, content on right

### Spacing System
Define a spacing scale using CSS custom properties:
```css
--space-1: 0.25rem;
--space-2: 0.5rem;
--space-4: 1rem;
--space-6: 1.5rem;
--space-8: 2rem;
```

Use ONLY these variables for all padding and margin.

### Layout
- Cards in a 3-column grid
- Consistent spacing between cards using `gap`
- Cards stretch to equal height in each row

---

## What Good Looks Like

- All cards use `box-sizing: border-box`
- Spacing is consistent and uses the spacing scale
- Cards look polished and professional
- The grid layout is clean

---

## Submission

Submit `card-system.html` and `card-system.css`.
