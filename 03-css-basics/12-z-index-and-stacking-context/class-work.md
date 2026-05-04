# Class Work — Build a Layered UI

## What You Will Build

A page with a sticky header, dropdown menu, modal, and toast notification — all properly layered with z-index.

**Time:** 30 minutes

---

## Step 1 — Create the HTML

Create `z-index-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>z-index Demo</title>
  <link rel="stylesheet" href="z-index.css">
</head>
<body>

  <!-- Layer 5: Sticky header -->
  <header class="sticky-header">
    <span>MyApp</span>
    <div class="dropdown-wrapper">
      <button class="dropdown-btn" onclick="this.nextElementSibling.classList.toggle('open')">
        Menu ▾
      </button>
      <!-- Layer 4: Dropdown -->
      <div class="dropdown-menu">
        <a href="#">Profile</a>
        <a href="#">Settings</a>
        <a href="#">Logout</a>
      </div>
    </div>
  </header>

  <main>
    <h1>z-index and Stacking Context</h1>
    <p>Click "Menu" to see the dropdown appear above the content.</p>
    <p>Click "Open Modal" to see the modal appear above the header.</p>

    <button onclick="document.getElementById('modal').style.display='flex'">
      Open Modal
    </button>

    <div class="content-cards">
      <div class="card">Card 1</div>
      <div class="card">Card 2</div>
      <div class="card">Card 3</div>
    </div>
  </main>

  <!-- Layer 6: Modal overlay -->
  <div class="modal-overlay" id="modal" onclick="this.style.display='none'">
    <!-- Layer 7: Modal dialog -->
    <div class="modal-dialog" onclick="event.stopPropagation()">
      <h2>Modal Dialog</h2>
      <p>This modal appears above the sticky header (z-index: 400 vs 200).</p>
      <button onclick="document.getElementById('modal').style.display='none'">Close</button>
    </div>
  </div>

  <!-- Layer 8: Toast notification -->
  <div class="toast" id="toast">
    ✓ Action completed successfully!
  </div>

  <script>
    // Show toast after 1 second
    setTimeout(() => {
      document.getElementById('toast').classList.add('show');
      setTimeout(() => document.getElementById('toast').classList.remove('show'), 3000);
    }, 1000);
  </script>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `z-index.css`:

```css
:root {
  --z-dropdown: 100;
  --z-sticky:   200;
  --z-overlay:  300;
  --z-modal:    400;
  --z-toast:    500;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
body { font-family: sans-serif; color: #333; }

/* Sticky header — z-index: 200 */
.sticky-header {
  position: sticky;
  top: 0;
  z-index: var(--z-sticky);
  background: #2c3e50;
  color: white;
  padding: 0 2rem;
  height: 64px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

/* Dropdown — z-index: 100 */
.dropdown-wrapper { position: relative; }

.dropdown-btn {
  background: transparent;
  color: white;
  border: 1px solid rgba(255,255,255,0.3);
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
}

.dropdown-menu {
  display: none;
  position: absolute;
  top: calc(100% + 8px);
  right: 0;
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  box-shadow: 0 8px 24px rgba(0,0,0,0.15);
  min-width: 160px;
  z-index: var(--z-dropdown);
}

.dropdown-menu.open { display: block; }

.dropdown-menu a {
  display: block;
  padding: 12px 16px;
  color: #333;
  text-decoration: none;
}

.dropdown-menu a:hover { background: #f5f5f5; }

main {
  max-width: 900px;
  margin: 0 auto;
  padding: 3rem 2rem;
}

h1 { margin-bottom: 1rem; }
p { margin-bottom: 1rem; }

button {
  padding: 10px 20px;
  background: #3498db;
  color: white;
  border: none;
  border-radius: 6px;
  cursor: pointer;
  margin-bottom: 2rem;
}

.content-cards {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 1rem;
}

.card {
  background: white;
  border: 1px solid #e0e0e0;
  border-radius: 8px;
  padding: 2rem;
  text-align: center;
}

/* Modal overlay — z-index: 300 */
.modal-overlay {
  display: none;
  position: fixed;
  inset: 0;
  background: rgba(0,0,0,0.5);
  z-index: var(--z-overlay);
  align-items: center;
  justify-content: center;
}

/* Modal dialog — z-index: 400 */
.modal-dialog {
  background: white;
  padding: 2rem;
  border-radius: 12px;
  max-width: 400px;
  width: 90%;
  z-index: var(--z-modal);
  position: relative;
}

.modal-dialog h2 { margin-bottom: 1rem; }
.modal-dialog p { margin-bottom: 1.5rem; color: #666; }

/* Toast — z-index: 500 */
.toast {
  position: fixed;
  bottom: 2rem;
  right: 2rem;
  background: #27ae60;
  color: white;
  padding: 12px 20px;
  border-radius: 8px;
  z-index: var(--z-toast);
  transform: translateY(100px);
  opacity: 0;
  transition: transform 0.3s, opacity 0.3s;
}

.toast.show {
  transform: translateY(0);
  opacity: 1;
}
```

---

## Checklist

- [ ] Sticky header has `z-index: var(--z-sticky)` (200)
- [ ] Dropdown has `z-index: var(--z-dropdown)` (100)
- [ ] Modal overlay has `z-index: var(--z-overlay)` (300)
- [ ] Modal dialog has `z-index: var(--z-modal)` (400)
- [ ] Toast has `z-index: var(--z-toast)` (500)
- [ ] All z-index values use CSS custom properties
- [ ] Modal appears above the sticky header
- [ ] Toast appears above the modal
