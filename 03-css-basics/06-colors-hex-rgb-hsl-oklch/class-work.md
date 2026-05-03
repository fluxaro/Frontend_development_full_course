# Class Work — Build a Color Palette

## What You Will Build

A color palette page showing all CSS color formats and how to create consistent color variations with HSL.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `color-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Colors Demo</title>
  <link rel="stylesheet" href="colors.css">
</head>
<body>
  <h1>CSS Color Formats</h1>

  <section>
    <h2>Named Colors</h2>
    <div class="swatch-row">
      <div class="swatch" style="background: tomato;"><span>tomato</span></div>
      <div class="swatch" style="background: cornflowerblue;"><span>cornflowerblue</span></div>
      <div class="swatch" style="background: mediumseagreen;"><span>mediumseagreen</span></div>
      <div class="swatch" style="background: goldenrod;"><span>goldenrod</span></div>
    </div>
  </section>

  <section>
    <h2>Hex Colors</h2>
    <div class="swatch-row">
      <div class="swatch" style="background: #e74c3c;"><span>#e74c3c</span></div>
      <div class="swatch" style="background: #3498db;"><span>#3498db</span></div>
      <div class="swatch" style="background: #2ecc71;"><span>#2ecc71</span></div>
      <div class="swatch" style="background: #f39c12;"><span>#f39c12</span></div>
    </div>
  </section>

  <section>
    <h2>RGB Colors</h2>
    <div class="swatch-row">
      <div class="swatch" style="background: rgb(231 76 60);"><span>rgb(231 76 60)</span></div>
      <div class="swatch" style="background: rgb(52 152 219);"><span>rgb(52 152 219)</span></div>
      <div class="swatch" style="background: rgb(46 204 113);"><span>rgb(46 204 113)</span></div>
    </div>
  </section>

  <section>
    <h2>HSL Colors — Blue Palette</h2>
    <div class="swatch-row">
      <div class="swatch" style="background: hsl(204 70% 95%);"><span>95% L</span></div>
      <div class="swatch" style="background: hsl(204 70% 80%);"><span>80% L</span></div>
      <div class="swatch" style="background: hsl(204 70% 65%);"><span>65% L</span></div>
      <div class="swatch" style="background: hsl(204 70% 53%);"><span>53% L</span></div>
      <div class="swatch" style="background: hsl(204 70% 40%);"><span>40% L</span></div>
      <div class="swatch" style="background: hsl(204 70% 25%);"><span>25% L</span></div>
    </div>
  </section>

  <section>
    <h2>oklch Colors</h2>
    <div class="swatch-row">
      <div class="swatch" style="background: oklch(0.65 0.2 30);"><span>oklch red</span></div>
      <div class="swatch" style="background: oklch(0.65 0.2 145);"><span>oklch green</span></div>
      <div class="swatch" style="background: oklch(0.65 0.2 230);"><span>oklch blue</span></div>
      <div class="swatch" style="background: oklch(0.65 0.2 300);"><span>oklch purple</span></div>
    </div>
  </section>

  <section>
    <h2>Transparency</h2>
    <div class="transparency-demo">
      <div style="background: rgb(52 152 219 / 20%);"><span>20%</span></div>
      <div style="background: rgb(52 152 219 / 40%);"><span>40%</span></div>
      <div style="background: rgb(52 152 219 / 60%);"><span>60%</span></div>
      <div style="background: rgb(52 152 219 / 80%);"><span>80%</span></div>
      <div style="background: rgb(52 152 219 / 100%);"><span>100%</span></div>
    </div>
  </section>
</body>
</html>
```

---

## Step 2 — Create the CSS

Create `colors.css`:

```css
* { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: sans-serif;
  padding: 40px;
  background: #f8f9fa;
}

h1 { margin-bottom: 40px; color: #2c3e50; }
h2 { margin-bottom: 16px; color: #555; font-size: 1rem; text-transform: uppercase; letter-spacing: 1px; }
section { margin-bottom: 40px; }

.swatch-row {
  display: flex;
  gap: 12px;
  flex-wrap: wrap;
}

.swatch {
  width: 120px;
  height: 80px;
  border-radius: 8px;
  display: flex;
  align-items: flex-end;
  padding: 8px;
  box-shadow: 0 2px 8px rgba(0,0,0,0.1);
}

.swatch span {
  font-size: 0.7rem;
  background: rgba(0,0,0,0.5);
  color: white;
  padding: 2px 6px;
  border-radius: 4px;
}

.transparency-demo {
  display: flex;
  gap: 12px;
  background: repeating-linear-gradient(
    45deg,
    #ccc 0px, #ccc 10px,
    #fff 10px, #fff 20px
  );
  padding: 20px;
  border-radius: 8px;
}

.transparency-demo div {
  width: 80px;
  height: 80px;
  border-radius: 8px;
  display: flex;
  align-items: center;
  justify-content: center;
}

.transparency-demo span {
  font-size: 0.8rem;
  font-weight: bold;
  color: #333;
}
```

---

## Checklist

- [ ] Named colors displayed
- [ ] Hex colors displayed
- [ ] RGB colors displayed
- [ ] HSL palette showing lightness variations
- [ ] oklch colors displayed
- [ ] Transparency demo with checkered background
