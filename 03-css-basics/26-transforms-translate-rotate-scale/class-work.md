# Class Work — Transform Effects

## What You Will Build

A demo page showing all CSS transform functions with interactive examples.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `transforms-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Transforms Demo</title>
  <link rel="stylesheet" href="transforms.css">
</head>
<body>

  <main>
    <h1>CSS Transforms</h1>

    <section>
      <h2>translate</h2>
      <div class="demo-row">
        <div class="box translate-x">translateX(30px)</div>
        <div class="box translate-y">translateY(-20px)</div>
        <div class="box translate-xy">translate(20px, -20px)</div>
        <div class="box translate-hover">Hover: translateY(-8px)</div>
      </div>
    </section>

    <section>
      <h2>scale</h2>
      <div class="demo-row">
        <div class="box scale-up">scale(1.3)</div>
        <div class="box scale-down">scale(0.7)</div>
        <div class="box scale-x">scaleX(1.5)</div>
        <div class="box scale-hover">Hover: scale(1.1)</div>
      </div>
    </section>

    <section>
      <h2>rotate</h2>
      <div class="demo-row">
        <div class="box rotate-45">rotate(45deg)</div>
        <div class="box rotate-neg">rotate(-30deg)</div>
        <div class="box rotate-hover">Hover: rotate(360deg)</div>
      </div>
    </section>

    <section>
      <h2>skew</h2>
      <div class="demo-row">
        <div class="box skew-x">skewX(15deg)</div>
        <div class="box skew-y">skewY(10deg)</div>
      </div>
    </section>

    <section>
      <h2>Centering with translate</h2>
      <div class="center-demo">
        <div class="centered-box">I am centered!</div>
      </div>
    </section>

    <section>
      <h2>3D Card Flip</h2>
      <div class="flip-card">
        <div class="flip-inner">
          <div class="flip-front">Front</div>
          <div class="flip-back">Back</div>
        </div>
      </div>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `transforms.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; padding: 40px; background: #f8f9fa; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 20px; color: #2c3e50; }
section { margin-bottom: 60px; }

.demo-row { display: flex; gap: 2rem; flex-wrap: wrap; align-items: center; }

.box {
  width: 120px;
  height: 80px;
  background: #3498db;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  font-size: 0.75rem;
  font-weight: bold;
  text-align: center;
  padding: 8px;
}

/* translate */
.translate-x  { transform: translateX(30px); }
.translate-y  { transform: translateY(-20px); }
.translate-xy { transform: translate(20px, -20px); }
.translate-hover { transition: transform 0.3s ease; cursor: pointer; }
.translate-hover:hover { transform: translateY(-8px); }

/* scale */
.scale-up   { transform: scale(1.3); background: #9b59b6; }
.scale-down { transform: scale(0.7); background: #e74c3c; }
.scale-x    { transform: scaleX(1.5); background: #27ae60; }
.scale-hover { transition: transform 0.3s ease; cursor: pointer; }
.scale-hover:hover { transform: scale(1.1); }

/* rotate */
.rotate-45  { transform: rotate(45deg); background: #f39c12; }
.rotate-neg { transform: rotate(-30deg); background: #e74c3c; }
.rotate-hover { transition: transform 0.6s ease; cursor: pointer; }
.rotate-hover:hover { transform: rotate(360deg); }

/* skew */
.skew-x { transform: skewX(15deg); background: #1abc9c; }
.skew-y { transform: skewY(10deg); background: #e67e22; }

/* Centering */
.center-demo {
  position: relative;
  height: 200px;
  background: #ecf0f1;
  border-radius: 8px;
}

.centered-box {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  background: #2c3e50;
  color: white;
  padding: 16px 32px;
  border-radius: 8px;
  font-weight: bold;
}

/* 3D Card Flip */
.flip-card {
  width: 200px;
  height: 130px;
  perspective: 600px;
  cursor: pointer;
}

.flip-inner {
  width: 100%;
  height: 100%;
  position: relative;
  transform-style: preserve-3d;
  transition: transform 0.6s ease;
}

.flip-card:hover .flip-inner {
  transform: rotateY(180deg);
}

.flip-front, .flip-back {
  position: absolute;
  inset: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 8px;
  font-size: 1.2rem;
  font-weight: bold;
  backface-visibility: hidden;
}

.flip-front { background: #3498db; color: white; }
.flip-back  { background: #e74c3c; color: white; transform: rotateY(180deg); }
```

---

## Checklist

- [ ] All transform functions demonstrated
- [ ] Hover effects use transitions
- [ ] Centering with `translate(-50%, -50%)` works
- [ ] 3D card flip works on hover
