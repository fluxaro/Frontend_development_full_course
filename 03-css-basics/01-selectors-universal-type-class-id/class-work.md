# Class Work — Style a Card Component with All Selector Types

## What You Will Build

A card component styled using all four selector types: universal, type, class, and ID.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `selectors-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Selectors Demo</title>
  <link rel="stylesheet" href="selectors.css">
</head>
<body>

  <header id="site-header">
    <h1>CSS Selectors Demo</h1>
    <nav>
      <a href="#cards">Cards</a>
      <a href="#buttons">Buttons</a>
    </nav>
  </header>

  <main id="main-content">

    <section id="cards">
      <h2>Card Components</h2>

      <div class="card">
        <h3 class="card-title">Basic Card</h3>
        <p class="card-text">This is a basic card with default styling.</p>
        <a href="#" class="btn">Read More</a>
      </div>

      <div class="card featured">
        <h3 class="card-title">Featured Card</h3>
        <p class="card-text">This card has both the "card" and "featured" classes.</p>
        <a href="#" class="btn btn-primary">Read More</a>
      </div>

      <div class="card">
        <h3 class="card-title">Another Card</h3>
        <p class="card-text">Cards are reusable components styled with classes.</p>
        <a href="#" class="btn">Read More</a>
      </div>
    </section>

    <section id="buttons">
      <h2>Button Variants</h2>
      <button class="btn">Default</button>
      <button class="btn btn-primary">Primary</button>
      <button class="btn btn-danger">Danger</button>
      <button class="btn btn-large">Large</button>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS File

Create `selectors.css`:

### Universal Selector

```css
/* Universal: applies to every element */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}
```

### Type Selectors

```css
/* Type selectors: target HTML elements */
body {
  font-family: sans-serif;
  background-color: #f0f2f5;
  color: #333;
  padding: 20px;
}

h1 {
  font-size: 2rem;
  color: white;
}

h2 {
  font-size: 1.5rem;
  margin-bottom: 20px;
  color: #2c3e50;
}

h3 {
  font-size: 1.2rem;
  margin-bottom: 10px;
}

p {
  line-height: 1.6;
  color: #666;
}

a {
  text-decoration: none;
  color: #3498db;
}
```

### ID Selectors

```css
/* ID selectors: unique elements */
#site-header {
  background-color: #2c3e50;
  padding: 20px 30px;
  margin-bottom: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

#site-header nav a {
  color: #bdc3c7;
  margin-left: 20px;
}

#main-content {
  max-width: 1000px;
  margin: 0 auto;
}

#cards {
  margin-bottom: 40px;
}
```

### Class Selectors

```css
/* Class selectors: reusable components */
.card {
  background: white;
  border-radius: 8px;
  padding: 24px;
  margin-bottom: 16px;
  border: 1px solid #e0e0e0;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

/* Multiple classes: .card.featured */
.card.featured {
  border-color: #3498db;
  border-width: 2px;
  background-color: #ebf5fb;
}

.card-title {
  color: #2c3e50;
  margin-bottom: 8px;
}

.card-text {
  margin-bottom: 16px;
}

/* Button base class */
.btn {
  display: inline-block;
  padding: 8px 16px;
  border: 1px solid #3498db;
  border-radius: 4px;
  color: #3498db;
  background: transparent;
  cursor: pointer;
  font-size: 0.9rem;
}

/* Modifier classes */
.btn-primary {
  background-color: #3498db;
  color: white;
  border-color: #3498db;
}

.btn-danger {
  background-color: #e74c3c;
  color: white;
  border-color: #e74c3c;
}

.btn-large {
  padding: 12px 24px;
  font-size: 1.1rem;
}
```

---

## Checklist

- [ ] Universal selector `*` used for box-sizing reset
- [ ] Type selectors used for body, h1, h2, p, a
- [ ] ID selectors used for `#site-header` and `#main-content`
- [ ] Class selectors used for `.card`, `.btn`, and variants
- [ ] Multiple classes on one element (`.card.featured`)
- [ ] Grouping selectors used at least once
