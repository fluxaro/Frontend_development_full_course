# Notes — Box Model

## Box Model Diagram

```
margin → border → padding → content
```

## box-sizing (Always Use border-box)

```css
*, *::before, *::after {
  box-sizing: border-box;
}
```

With `border-box`: `width` includes padding and border.  
With `content-box` (default): `width` is content only, padding/border add to total.

## Padding Shorthand

```css
padding: 10px;              /* all sides */
padding: 10px 20px;         /* top/bottom | left/right */
padding: 10px 20px 15px;    /* top | left/right | bottom */
padding: 10px 20px 15px 5px;/* top | right | bottom | left */
```

## Margin Shorthand

Same pattern as padding. Plus:

```css
margin: 0 auto;  /* center horizontally */
margin-inline: auto;  /* modern centering */
```

## Border Shorthand

```css
border: 2px solid #3498db;
/* width | style | color */
```

## Margin Collapse

Vertical margins between siblings collapse to the larger value. Does NOT happen in flex/grid.

## Common Patterns

```css
/* Reset */
* { box-sizing: border-box; margin: 0; padding: 0; }

/* Center container */
.container {
  max-width: 1200px;
  margin-inline: auto;
  padding-inline: 1rem;
}

/* Card */
.card {
  padding: 1.5rem;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
}
```

## Common Mistakes

- Forgetting `box-sizing: border-box` (elements wider than expected)
- Using margin for internal spacing (use padding instead)
- Not understanding margin collapse
- Using `border: none` vs `border: 0` (both work, `none` is clearer)
