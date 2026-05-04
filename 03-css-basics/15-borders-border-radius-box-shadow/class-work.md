# Class Work — Card Component with Borders and Shadows

## What You Will Build

A card component library demonstrating all border and shadow techniques.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `borders-shadows-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Borders and Shadows Demo</title>
  <link rel="stylesheet" href="borders-shadows.css">
</head>
<body>

  <main>
    <h1>Borders, Border-radius, and Box-shadow</h1>

    <section>
      <h2>Border Styles</h2>
      <div class="demo-grid">
        <div class="border-solid">solid</div>
        <div class="border-dashed">dashed</div>
        <div class="border-dotted">dotted</div>
        <div class="border-double">double</div>
        <div class="border-top-only">top only</div>
        <div class="border-left-accent">left accent</div>
      </div>
    </section>

    <section>
      <h2>Border Radius</h2>
      <div class="demo-grid">
        <div class="radius-sm">4px</div>
        <div class="radius-md">8px</div>
        <div class="radius-lg">16px</div>
        <div class="radius-xl">24px</div>
        <div class="radius-full">9999px (pill)</div>
        <div class="radius-circle">50% (circle)</div>
        <div class="radius-custom">Custom corners</div>
      </div>
    </section>

    <section>
      <h2>Box Shadows</h2>
      <div class="demo-grid">
        <div class="shadow-sm">Small shadow</div>
        <div class="shadow-md">Medium shadow</div>
        <div class="shadow-lg">Large shadow</div>
        <div class="shadow-xl">XL shadow</div>
        <div class="shadow-colored">Colored shadow</div>
        <div class="shadow-inset">Inset shadow</div>
        <div class="shadow-multiple">Multiple shadows</div>
        <div class="shadow-hover">Hover me</div>
      </div>
    </section>

    <section>
      <h2>Card Variants</h2>
      <div class="card-grid">
        <div class="card card-flat">
          <h3>Flat Card</h3>
          <p>Border only, no shadow.</p>
        </div>
        <div class="card card-elevated">
          <h3>Elevated Card</h3>
          <p>Shadow only, no border.</p>
        </div>
        <div class="card card-outlined">
          <h3>Outlined Card</h3>
          <p>Colored border, no shadow.</p>
        </div>
        <div class="card card-glass">
          <h3>Glass Card</h3>
          <p>Backdrop blur effect.</p>
        </div>
      </div>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `borders-shadows.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f0f2f5; color: #333; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 20px; color: #2c3e50; }
section { margin-bottom: 50px; }

.demo-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(150px, 1fr));
  gap: 16px;
}

.demo-grid div {
  background: white;
  padding: 20px;
  text-align: center;
  font-size: 0.85rem;
  font-weight: 600;
}

/* Border styles */
.border-solid      { border: 2px solid #3498db; }
.border-dashed     { border: 2px dashed #e74c3c; }
.border-dotted     { border: 2px dotted #27ae60; }
.border-double     { border: 6px double #9b59b6; }
.border-top-only   { border-top: 4px solid #f39c12; }
.border-left-accent { border-left: 4px solid #3498db; padding-left: 16px; }

/* Border radius */
.radius-sm     { border: 2px solid #3498db; border-radius: 4px; }
.radius-md     { border: 2px solid #3498db; border-radius: 8px; }
.radius-lg     { border: 2px solid #3498db; border-radius: 16px; }
.radius-xl     { border: 2px solid #3498db; border-radius: 24px; }
.radius-full   { border: 2px solid #3498db; border-radius: 9999px; }
.radius-circle { border: 2px solid #3498db; border-radius: 50%; width: 80px; height: 80px; margin: 0 auto; display: flex; align-items: center; justify-content: center; }
.radius-custom { border: 2px solid #3498db; border-radius: 0 16px 0 16px; }

/* Box shadows */
.shadow-sm       { box-shadow: 0 1px 3px rgba(0,0,0,0.1); }
.shadow-md       { box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
.shadow-lg       { box-shadow: 0 8px 24px rgba(0,0,0,0.15); }
.shadow-xl       { box-shadow: 0 20px 60px rgba(0,0,0,0.2); }
.shadow-colored  { box-shadow: 0 8px 24px rgba(52, 152, 219, 0.4); }
.shadow-inset    { box-shadow: inset 0 2px 8px rgba(0,0,0,0.15); }
.shadow-multiple { box-shadow: 0 1px 3px rgba(0,0,0,0.1), 0 8px 24px rgba(0,0,0,0.1); }
.shadow-hover    { transition: box-shadow 0.3s, transform 0.3s; cursor: pointer; }
.shadow-hover:hover { box-shadow: 0 12px 40px rgba(0,0,0,0.2); transform: translateY(-4px); }

/* Card variants */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(220px, 1fr));
  gap: 20px;
}

.card {
  padding: 24px;
  border-radius: 12px;
  background: white;
}

.card h3 { margin-bottom: 8px; }
.card p  { color: #666; font-size: 0.9rem; }

.card-flat     { border: 1px solid #e0e0e0; }
.card-elevated { box-shadow: 0 8px 24px rgba(0,0,0,0.1); }
.card-outlined { border: 2px solid #3498db; }
.card-glass    {
  background: rgba(255,255,255,0.7);
  backdrop-filter: blur(10px);
  border: 1px solid rgba(255,255,255,0.5);
  box-shadow: 0 8px 32px rgba(0,0,0,0.1);
}
```

---

## Checklist

- [ ] All border styles demonstrated
- [ ] Border radius variations shown
- [ ] Multiple shadow levels shown
- [ ] Colored shadow shown
- [ ] Inset shadow shown
- [ ] Hover shadow transition works
- [ ] Glass card with backdrop-filter
