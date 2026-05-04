# Class Work — Units Comparison Demo

## What You Will Build

A page that visually demonstrates the difference between px, rem, em, vw, and clamp.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `units-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Units Demo</title>
  <link rel="stylesheet" href="units.css">
</head>
<body>

  <header class="hero">
    <h1>CSS Units Demo</h1>
    <p>Resize the browser window to see how different units behave.</p>
  </header>

  <main>

    <section>
      <h2>Font Size Comparison</h2>
      <p class="size-px">16px — fixed, does not scale</p>
      <p class="size-rem">1rem — scales with root font size</p>
      <p class="size-em">1em — scales with parent font size</p>
      <p class="size-vw">2vw — scales with viewport width</p>
      <p class="size-clamp">clamp(1rem, 2.5vw, 2rem) — fluid</p>
    </section>

    <section>
      <h2>Width Comparison</h2>
      <div class="width-px">300px — fixed width</div>
      <div class="width-percent">50% — half of parent</div>
      <div class="width-vw">50vw — half of viewport</div>
      <div class="width-rem">20rem — 320px at default</div>
      <div class="width-ch">65ch — ideal reading width</div>
    </section>

    <section>
      <h2>Viewport Height</h2>
      <div class="height-vh">100vh — may have mobile issues</div>
      <div class="height-dvh">100dvh — mobile safe</div>
    </section>

    <section>
      <h2>Fluid Typography with clamp()</h2>
      <h1 class="fluid-h1">Fluid Heading</h1>
      <p class="fluid-p">This paragraph text scales fluidly between 16px and 20px.</p>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `units.css`:

```css
:root {
  font-size: 16px; /* base for rem calculations */
}

* { box-sizing: border-box; margin: 0; padding: 0; }

body { font-family: sans-serif; color: #333; }

/* Hero with dvh */
.hero {
  height: 100dvh;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  background: #2c3e50;
  color: white;
  text-align: center;
  padding: 2rem;
}

.hero h1 {
  font-size: clamp(2rem, 6vw, 5rem);
  margin-bottom: 1rem;
}

main {
  max-width: 900px;
  margin: 0 auto;
  padding: 3rem 2rem;
}

section {
  margin-bottom: 3rem;
}

h2 {
  font-size: 1.5rem;
  margin-bottom: 1.5rem;
  color: #2c3e50;
  border-bottom: 2px solid #3498db;
  padding-bottom: 0.5rem;
}

/* Font size demos */
.size-px    { font-size: 16px;                        background: #ebf5fb; padding: 8px; margin-bottom: 8px; }
.size-rem   { font-size: 1rem;                        background: #eafaf1; padding: 8px; margin-bottom: 8px; }
.size-em    { font-size: 1em;                         background: #fef9e7; padding: 8px; margin-bottom: 8px; }
.size-vw    { font-size: 2vw;                         background: #fdf2f8; padding: 8px; margin-bottom: 8px; }
.size-clamp { font-size: clamp(1rem, 2.5vw, 2rem);   background: #f9f9f9; padding: 8px; margin-bottom: 8px; }

/* Width demos */
.width-px      { width: 300px;  background: #ebf5fb; padding: 12px; margin-bottom: 8px; }
.width-percent { width: 50%;    background: #eafaf1; padding: 12px; margin-bottom: 8px; }
.width-vw      { width: 50vw;   background: #fef9e7; padding: 12px; margin-bottom: 8px; }
.width-rem     { width: 20rem;  background: #fdf2f8; padding: 12px; margin-bottom: 8px; }
.width-ch      { width: 65ch;   background: #f9f9f9; padding: 12px; margin-bottom: 8px; }

/* Height demos */
.height-vh, .height-dvh {
  height: 200px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 8px;
  border-radius: 8px;
  font-weight: bold;
}
.height-vh  { background: #ebf5fb; }
.height-dvh { background: #eafaf1; }

/* Fluid typography */
.fluid-h1 { font-size: clamp(2rem, 5vw, 4rem); margin-bottom: 1rem; }
.fluid-p  { font-size: clamp(1rem, 1.5vw, 1.25rem); max-width: 65ch; line-height: 1.7; }
```

---

## Checklist

- [ ] Hero uses `dvh` for full-screen height
- [ ] Hero heading uses `clamp()` for fluid size
- [ ] Font size comparison shows all 5 units
- [ ] Width comparison shows px, %, vw, rem, ch
- [ ] Fluid typography section demonstrates `clamp()`
- [ ] Resize browser to see units behave differently
