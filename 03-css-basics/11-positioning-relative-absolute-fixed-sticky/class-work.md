# Class Work — Build a Sticky Nav and Card with Badge

## What You Will Build

A page with a sticky navigation, cards with absolute-positioned badges, and a fixed back-to-top button.

**Time:** 35 minutes

---

## Step 1 — Create the HTML

Create `positioning-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Positioning Demo</title>
  <link rel="stylesheet" href="positioning.css">
</head>
<body>

  <!-- FIXED: stays at top when scrolling -->
  <nav class="navbar">
    <div class="nav-container">
      <span class="logo">MyApp</span>
      <ul>
        <li><a href="#section1">Section 1</a></li>
        <li><a href="#section2">Section 2</a></li>
        <li><a href="#section3">Section 3</a></li>
      </ul>
    </div>
  </nav>

  <!-- FIXED: back to top button -->
  <a href="#top" class="back-to-top">↑</a>

  <main id="top">

    <section id="section1">
      <h2>Cards with Absolute Badges</h2>
      <div class="card-grid">

        <div class="card">
          <span class="badge badge-new">NEW</span>
          <h3>Product Card</h3>
          <p>The badge is positioned absolutely at the top-right corner of the card.</p>
          <p>The card has <code>position: relative</code> to create the positioning context.</p>
        </div>

        <div class="card">
          <span class="badge badge-sale">SALE</span>
          <h3>Sale Item</h3>
          <p>Another card with a different badge variant.</p>
        </div>

        <div class="card">
          <span class="badge badge-hot">HOT</span>
          <h3>Popular Item</h3>
          <p>Badges can be styled differently while using the same positioning.</p>
        </div>

      </div>
    </section>

    <section id="section2">
      <h2>Sticky Sidebar Layout</h2>
      <div class="sidebar-layout">
        <aside class="sticky-sidebar">
          <h3>Sticky Sidebar</h3>
          <p>This sidebar sticks as you scroll.</p>
          <nav>
            <ul>
              <li><a href="#">Link 1</a></li>
              <li><a href="#">Link 2</a></li>
              <li><a href="#">Link 3</a></li>
            </ul>
          </nav>
        </aside>
        <div class="main-content">
          <h3>Main Content</h3>
          <p>Scroll down to see the sidebar stick. Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
          <p>Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
          <p>Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.</p>
          <p>Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.</p>
          <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.</p>
        </div>
      </div>
    </section>

    <section id="section3">
      <h2>Centered Modal Pattern</h2>
      <button class="open-modal-btn" onclick="document.getElementById('modal').style.display='flex'">
        Open Modal
      </button>

      <div class="modal-overlay" id="modal" onclick="this.style.display='none'">
        <div class="modal-box" onclick="event.stopPropagation()">
          <h3>Modal Title</h3>
          <p>This modal uses <code>position: fixed</code> for the overlay and <code>transform: translate(-50%, -50%)</code> for centering.</p>
          <button onclick="document.getElementById('modal').style.display='none'">Close</button>
        </div>
      </div>
    </section>

  </main>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `positioning.css`:

```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body { font-family: sans-serif; color: #333; }

/* FIXED navbar */
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 64px;
  background: #2c3e50;
  z-index: 100;
  display: flex;
  align-items: center;
}

.nav-container {
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 2rem;
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
}

.logo { color: white; font-size: 1.2rem; font-weight: bold; }

.navbar ul { list-style: none; display: flex; gap: 1rem; }
.navbar a { color: #bdc3c7; text-decoration: none; }
.navbar a:hover { color: white; }

/* FIXED back-to-top */
.back-to-top {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  width: 48px;
  height: 48px;
  background: #3498db;
  color: white;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  text-decoration: none;
  font-size: 1.2rem;
  z-index: 100;
  box-shadow: 0 4px 12px rgba(0,0,0,0.2);
}

main {
  max-width: 1200px;
  margin: 0 auto;
  padding: 80px 2rem 4rem;
}

section { margin-bottom: 4rem; }
h2 { font-size: 1.5rem; margin-bottom: 1.5rem; color: #2c3e50; }

/* Cards with ABSOLUTE badges */
.card-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
  gap: 1.5rem;
}

.card {
  position: relative;  /* creates positioning context for badge */
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.5rem;
  box-shadow: 0 2px 8px rgba(0,0,0,0.05);
}

.card h3 { margin-bottom: 0.75rem; }
.card p { color: #666; margin-bottom: 0.5rem; font-size: 0.9rem; }

/* ABSOLUTE badge */
.badge {
  position: absolute;
  top: -10px;
  right: -10px;
  padding: 4px 10px;
  border-radius: 20px;
  font-size: 0.7rem;
  font-weight: bold;
  color: white;
}

.badge-new  { background: #3498db; }
.badge-sale { background: #e74c3c; }
.badge-hot  { background: #f39c12; }

/* STICKY sidebar */
.sidebar-layout {
  display: grid;
  grid-template-columns: 250px 1fr;
  gap: 2rem;
  align-items: start;
}

.sticky-sidebar {
  position: sticky;
  top: 80px;  /* 64px nav + 16px gap */
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 1.5rem;
}

.sticky-sidebar h3 { margin-bottom: 1rem; }
.sticky-sidebar ul { list-style: none; }
.sticky-sidebar li { margin-bottom: 0.5rem; }
.sticky-sidebar a { color: #3498db; text-decoration: none; }

.main-content p { margin-bottom: 1rem; line-height: 1.7; }

/* FIXED modal overlay */
.modal-overlay {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  z-index: 200;
  align-items: center;
  justify-content: center;
}

.modal-box {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  max-width: 400px;
  width: 90%;
  box-shadow: 0 20px 60px rgba(0,0,0,0.3);
}

.modal-box h3 { margin-bottom: 1rem; }
.modal-box p { margin-bottom: 1.5rem; color: #666; }

.open-modal-btn, .modal-box button {
  padding: 10px 20px;
  background: #3498db;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  font-size: 1rem;
}
```

---

## Checklist

- [ ] Navbar is `position: fixed` and stays at top when scrolling
- [ ] Back-to-top button is `position: fixed` at bottom-right
- [ ] Cards have `position: relative`
- [ ] Badges are `position: absolute` at top-right of cards
- [ ] Sidebar is `position: sticky`
- [ ] Modal overlay is `position: fixed` covering the whole screen
