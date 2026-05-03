# Class Work — Three Ways to Add CSS

## What You Will Build

You will style the same HTML page three different ways — inline, internal, and external — and observe the differences.

**Time:** 35 minutes

---

## Step 1 — Create the Base HTML

Create a file called `css-methods.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Methods Demo</title>
</head>
<body>
  <h1>CSS Methods Demo</h1>
  <p>This page demonstrates three ways to add CSS.</p>

  <h2>Method 1: Inline CSS</h2>
  <p>Styles applied directly to the element.</p>

  <h2>Method 2: Internal CSS</h2>
  <p>Styles in a style tag in the head.</p>

  <h2>Method 3: External CSS</h2>
  <p>Styles in a separate CSS file.</p>
</body>
</html>
```

Open in browser. It looks plain — just browser defaults.

---

## Step 2 — Add Inline CSS

Add `style` attributes directly to the first section's elements:

```html
<h2 style="color: #e74c3c; font-size: 1.5rem;">Method 1: Inline CSS</h2>
<p style="color: #666; background-color: #fff3cd; padding: 10px; border-left: 4px solid #ffc107;">
  Styles applied directly to the element. Notice how the style attribute is on the element itself.
</p>
```

**Observe:** The style only affects this specific element.

---

## Step 3 — Add Internal CSS

Add a `<style>` block in the `<head>`:

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>CSS Methods Demo</title>
  <style>
    body {
      font-family: sans-serif;
      max-width: 800px;
      margin: 0 auto;
      padding: 20px;
    }

    h1 {
      color: #2c3e50;
      border-bottom: 3px solid #3498db;
      padding-bottom: 10px;
    }

    h2 {
      color: #2980b9;
    }

    p {
      color: #555;
      line-height: 1.6;
    }
  </style>
</head>
```

**Observe:** These styles apply to the whole page.

---

## Step 4 — Add External CSS

Create a new file called `style.css` in the same folder:

```css
/* style.css */

/* Reset */
* {
  box-sizing: border-box;
}

/* Body */
body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background-color: #f8f9fa;
  color: #333;
  line-height: 1.6;
}

/* Headings */
h1 {
  color: #1a1a2e;
  font-size: 2.5rem;
}

h2 {
  color: #16213e;
  margin-top: 2rem;
}

/* Paragraphs */
p {
  color: #555;
  margin-bottom: 1rem;
}
```

Link it in the HTML `<head>`:

```html
<link rel="stylesheet" href="style.css">
```

**Observe:** The external CSS applies to the whole page and can be reused across multiple HTML files.

---

## Step 5 — Observe the Cascade

Now you have all three methods active. Notice:
- The inline style on the first `<h2>` overrides the internal and external styles
- The internal `<style>` block overrides the external `style.css` for the same properties
- External CSS applies to everything not overridden

---

## Checklist

- [ ] Inline CSS applied to at least one element
- [ ] Internal `<style>` block in `<head>`
- [ ] External `style.css` file created and linked
- [ ] All three methods are visible and working
- [ ] You can explain which method takes priority and why
