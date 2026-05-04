# Class Work — Box Model Explorer

## What You Will Build

A visual box model explorer that shows how padding, margin, and border affect element sizing.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `box-model-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Box Model Demo</title>
  <link rel="stylesheet" href="box-model.css">
</head>
<body>

  <h1>CSS Box Model Explorer</h1>

  <section>
    <h2>content-box vs border-box</h2>
    <div class="comparison">
      <div class="content-box-demo">
        <p>content-box</p>
        <small>width: 200px + padding: 20px + border: 2px = 244px total</small>
      </div>
      <div class="border-box-demo">
        <p>border-box</p>
        <small>width: 200px (includes padding and border)</small>
      </div>
    </div>
  </section>

  <section>
    <h2>Padding Demo</h2>
    <div class="padding-demo">
      <div class="pad-all">padding: 20px (all sides)</div>
      <div class="pad-vh">padding: 10px 40px (vertical | horizontal)</div>
      <div class="pad-individual">padding-top: 30px; padding-left: 60px</div>
    </div>
  </section>

  <section>
    <h2>Margin Demo</h2>
    <div class="margin-container">
      <div class="margin-demo">Box 1 (margin-bottom: 40px)</div>
      <div class="margin-demo">Box 2 (margin-top: 20px)</div>
      <p class="collapse-note">Gap = 40px (collapsed, not 60px)</p>
    </div>
  </section>

  <section>
    <h2>Border Styles</h2>
    <div class="border-demos">
      <div class="border-solid">solid</div>
      <div class="border-dashed">dashed</div>
      <div class="border-dotted">dotted</div>
      <div class="border-double">double</div>
      <div class="border-groove">groove</div>
    </div>
  </section>

  <section>
    <h2>Centering with margin: auto</h2>
    <div class="centered-box">I am centered with margin: 0 auto</div>
  </section>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `box-model.css`:

```css
*, *::before, *::after { box-sizing: border-box; }

body {
  font-family: sans-serif;
  padding: 40px;
  background: #f8f9fa;
  color: #333;
}

h1 { margin-bottom: 40px; }
h2 { margin-bottom: 20px; color: #2c3e50; }
section { margin-bottom: 50px; }

/* content-box vs border-box */
.comparison { display: flex; gap: 20px; flex-wrap: wrap; }

.content-box-demo {
  box-sizing: content-box;
  width: 200px;
  padding: 20px;
  border: 2px solid #e74c3c;
  background: #fdf2f2;
}

.border-box-demo {
  box-sizing: border-box;
  width: 200px;
  padding: 20px;
  border: 2px solid #27ae60;
  background: #f0faf4;
}

/* Padding demos */
.padding-demo { display: flex; flex-direction: column; gap: 10px; }

.pad-all, .pad-vh, .pad-individual {
  background: #ebf5fb;
  border: 2px solid #3498db;
}

.pad-all { padding: 20px; }
.pad-vh { padding: 10px 40px; }
.pad-individual { padding-top: 30px; padding-left: 60px; padding-bottom: 10px; padding-right: 10px; }

/* Margin demos */
.margin-container { background: #f0f0f0; padding: 10px; }

.margin-demo {
  background: #3498db;
  color: white;
  padding: 15px;
  text-align: center;
}

.margin-demo:first-child { margin-bottom: 40px; }
.margin-demo:nth-child(2) { margin-top: 20px; }

.collapse-note {
  font-size: 0.85rem;
  color: #666;
  margin-top: 10px;
  font-style: italic;
}

/* Border styles */
.border-demos { display: flex; gap: 15px; flex-wrap: wrap; }

.border-demos div {
  padding: 20px 30px;
  background: white;
  font-weight: bold;
}

.border-solid  { border: 3px solid #3498db; }
.border-dashed { border: 3px dashed #e74c3c; }
.border-dotted { border: 3px dotted #27ae60; }
.border-double { border: 6px double #9b59b6; }
.border-groove { border: 6px groove #f39c12; }

/* Centered box */
.centered-box {
  width: 400px;
  margin: 0 auto;
  padding: 20px;
  background: #2c3e50;
  color: white;
  text-align: center;
  border-radius: 8px;
}
```

---

## Checklist

- [ ] `box-sizing: border-box` applied globally
- [ ] content-box vs border-box comparison visible
- [ ] Padding shorthand variations demonstrated
- [ ] Margin collapse demonstrated
- [ ] All border styles shown
- [ ] Centering with `margin: 0 auto` works
