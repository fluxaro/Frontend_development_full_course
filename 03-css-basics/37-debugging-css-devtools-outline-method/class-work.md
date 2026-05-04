# Class Work — Debug a Broken Layout

## What You Will Do

Debug a page with intentional CSS bugs using DevTools and the outline method.

**Time:** 30 minutes

---

## Step 1 — Create the Broken Page

Create `broken-layout.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Broken Layout — Debug Me</title>
  <link rel="stylesheet" href="broken.css">
</head>
<body>
  <nav class="navbar">
    <span class="logo">Brand</span>
    <ul>
      <li><a href="#">Home</a></li>
      <li><a href="#">About</a></li>
    </ul>
  </nav>

  <main>
    <div class="card-grid">
      <div class="card">
        <img src="https://images.unsplash.com/photo-1461749280684-dccba630e2f6?w=300&h=200&fit=crop" alt="Code" width="300" height="200">
        <h2>Card Title</h2>
        <p>Card content here.</p>
        <button class="btn">Action</button>
      </div>
      <div class="card">
        <img src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?w=300&h=200&fit=crop" alt="Developer" width="300" height="200">
        <h2>Card Title</h2>
        <p>Card content here.</p>
        <button class="btn">Action</button>
      </div>
    </div>
  </main>
</body>
</html>
```

---

## Step 2 — Create the Broken CSS

Create `broken.css` with intentional bugs:

```css
/* Bug 1: Missing box-sizing */
/* (no box-sizing: border-box) */

body { font-family: sans-serif; padding: 40px; }

.navbar {
  background: #2c3e50;
  padding: 0 2rem;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
  margin-bottom: 2rem;
}

.logo { color: white; font-weight: bold; }
.navbar ul { list-style: none; display: flex; gap: 1.5rem; }
.navbar a { color: #bdc3c7; text-decoration: none; }

.card-grid {
  display: flex;
  gap: 1rem;
}

.card {
  /* Bug 2: width: 50% + padding causes overflow */
  width: 50%;
  padding: 20px;
  border: 1px solid #ddd;
  border-radius: 8px;
}

.card img {
  /* Bug 3: image has gap below (inline element) */
  width: 100%;
}

.card h2 { margin-bottom: 8px; }
.card p  { color: #666; margin-bottom: 16px; }

.btn {
  padding: 8px 20px;
  background: #3498db;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
}

/* Bug 4: z-index not working on badge */
.badge {
  position: relative;
  z-index: 10;
  background: red;
  color: white;
  padding: 2px 8px;
  border-radius: 4px;
}
```

---

## Step 3 — Debug Each Bug

### Bug 1: Cards overflow their container

**Symptom:** Cards are wider than 50% of the container.  
**Cause:** Without `box-sizing: border-box`, padding is added to the width.  
**Fix:** Add `*, *::before, *::after { box-sizing: border-box; }` at the top.

### Bug 2: Image has a gap below it

**Symptom:** There is a small gap between the image and the card border.  
**Cause:** Images are inline elements by default. Inline elements sit on the text baseline, leaving space for descenders.  
**Fix:** Add `display: block` to the image.

### Bug 3: z-index not working

**Symptom:** The badge does not appear above other elements.  
**Cause:** `z-index` only works on positioned elements.  
**Fix:** The badge already has `position: relative` — but if it did not, adding it would fix the issue.

---

## Step 4 — Use the Outline Method

Add this to the top of your CSS to see all element boxes:

```css
* { outline: 1px solid red; }
```

This reveals:
- Which elements are taking up space
- Where margins and padding are
- Which elements are overflowing

Remove it when done debugging.

---

## Checklist

- [ ] Found and fixed the box-sizing bug
- [ ] Found and fixed the image gap bug
- [ ] Used the outline method to visualize layout
- [ ] Used DevTools to inspect computed styles
