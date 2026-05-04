# Class Work — Display Property Demo

## What You Will Build

A page demonstrating all display values with visual examples.

**Time:** 25 minutes

---

## Step 1 — Create the HTML

Create `display-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Display Property Demo</title>
  <link rel="stylesheet" href="display.css">
</head>
<body>

  <h1>CSS Display Property</h1>

  <section>
    <h2>display: block</h2>
    <p>Block elements take up the full width and start on a new line.</p>
    <div class="block-demo">I am a div (block)</div>
    <div class="block-demo">I am another div (block)</div>
    <p class="block-demo">I am a p (block)</p>
  </section>

  <section>
    <h2>display: inline</h2>
    <p>Inline elements sit within text flow. Width and height have no effect.</p>
    <p>
      This is text with
      <span class="inline-demo">an inline span</span>
      and more text and
      <span class="inline-demo">another span</span>
      all on the same line.
    </p>
  </section>

  <section>
    <h2>display: inline-block</h2>
    <p>Inline-block sits inline but accepts width and height.</p>
    <span class="inline-block-demo">Badge 1</span>
    <span class="inline-block-demo">Badge 2</span>
    <span class="inline-block-demo">Badge 3</span>
  </section>

  <section>
    <h2>display: none vs visibility: hidden</h2>
    <div class="box-visible">I am visible</div>
    <div class="box-hidden">I am display: none (no space)</div>
    <div class="box-invisible">I am visibility: hidden (keeps space)</div>
    <div class="box-visible">I am visible again</div>
  </section>

  <section>
    <h2>Horizontal Navigation with inline-block</h2>
    <nav>
      <ul class="horizontal-nav">
        <li><a href="#">Home</a></li>
        <li><a href="#">About</a></li>
        <li><a href="#">Services</a></li>
        <li><a href="#">Contact</a></li>
      </ul>
    </nav>
  </section>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `display.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body { font-family: sans-serif; padding: 40px; color: #333; }
h1 { margin-bottom: 40px; }
h2 { margin-bottom: 15px; color: #2c3e50; }
section { margin-bottom: 50px; }
p { margin-bottom: 10px; }

/* Block */
.block-demo {
  background: #ebf5fb;
  border: 2px solid #3498db;
  padding: 10px;
  margin-bottom: 8px;
  /* display: block is default for div and p */
}

/* Inline */
.inline-demo {
  background: #fef9e7;
  border: 2px solid #f39c12;
  padding: 2px 8px;
  /* display: inline is default for span */
  /* Try adding width: 200px — it has no effect */
}

/* Inline-block */
.inline-block-demo {
  display: inline-block;
  background: #eafaf1;
  border: 2px solid #27ae60;
  padding: 6px 16px;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: bold;
  margin-right: 8px;
  /* Now width and height work */
}

/* None vs hidden */
.box-visible {
  background: #3498db;
  color: white;
  padding: 15px;
  margin-bottom: 8px;
  text-align: center;
}

.box-hidden {
  display: none;
  background: #e74c3c;
  color: white;
  padding: 15px;
  margin-bottom: 8px;
}

.box-invisible {
  visibility: hidden;
  background: #9b59b6;
  color: white;
  padding: 15px;
  margin-bottom: 8px;
}

/* Horizontal nav */
.horizontal-nav {
  list-style: none;
  background: #2c3e50;
  padding: 0;
}

.horizontal-nav li {
  display: inline-block;
}

.horizontal-nav a {
  display: block;
  padding: 14px 20px;
  color: white;
  text-decoration: none;
}

.horizontal-nav a:hover {
  background: #34495e;
}
```

---

## Checklist

- [ ] Block elements take full width
- [ ] Inline elements sit in text flow
- [ ] Inline-block elements accept width/height
- [ ] `display: none` removes element from layout
- [ ] `visibility: hidden` keeps space but hides element
- [ ] Horizontal nav built with `inline-block` on `<li>`
