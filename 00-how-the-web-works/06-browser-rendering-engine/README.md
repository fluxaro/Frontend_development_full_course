# 06 — How the Browser Renders a Page

## What Is This Lesson About?

When your browser receives HTML from a server, it does not just display it instantly. It goes through a precise series of steps called the **Critical Rendering Path** to turn raw code into pixels on your screen. Understanding this process helps you write faster, more efficient websites.

---

## The Critical Rendering Path — Step by Step

### Step 1: Parse HTML → Build the DOM

The browser reads the HTML file from top to bottom and builds a tree structure called the **DOM (Document Object Model)**. Every HTML element becomes a node in this tree.

```
HTML:
<html>
  <body>
    <h1>Hello</h1>
    <p>World</p>
  </body>
</html>

DOM Tree:
html
└── body
    ├── h1 → "Hello"
    └── p  → "World"
```

If the browser encounters a `<script>` tag, it **stops** parsing HTML and executes the script first. This is why scripts are placed at the bottom of the body or use `defer`/`async`.

### Step 2: Parse CSS → Build the CSSOM

While building the DOM, the browser also downloads and parses CSS files, building the **CSSOM (CSS Object Model)** — a tree of all CSS rules and their computed values.

CSS is **render-blocking** — the browser will not render anything until all CSS is downloaded and parsed.

### Step 3: Combine DOM + CSSOM → Render Tree

The browser combines the DOM and CSSOM into a **Render Tree**. This tree only contains visible elements — `display: none` elements are excluded.

### Step 4: Layout (Reflow)

The browser calculates the exact position and size of every element on the page. This is called **layout** or **reflow**. It answers: "Where does each box go? How big is it?"

### Step 5: Paint

The browser fills in the pixels — colors, text, images, borders, shadows. This is called **paint** or **rasterization**.

### Step 6: Composite

If the page has layers (from CSS transforms, opacity, z-index), the browser composites them together in the correct order to produce the final image.

---

## Why This Matters for Developers

| Action | What It Triggers | Cost |
|---|---|---|
| Change element color | Paint only | Low |
| Change element size | Layout + Paint | Medium |
| Change element position | Layout + Paint | Medium |
| CSS transform/opacity | Composite only | Very Low |
| Add/remove DOM elements | Layout + Paint | High |

**Key insight:** CSS `transform` and `opacity` are the cheapest properties to animate because they skip Layout and Paint — they only trigger Compositing.

---

## Key Terms

- **DOM** — Document Object Model. A tree representation of your HTML.
- **CSSOM** — CSS Object Model. A tree representation of your CSS.
- **Render Tree** — The combined DOM + CSSOM, containing only visible elements.
- **Layout / Reflow** — Calculating position and size of elements.
- **Paint / Rasterize** — Drawing pixels on screen.
- **Composite** — Combining layers into the final image.
- **Render-blocking** — Resources that prevent the browser from rendering until they are loaded.
- **Critical Rendering Path** — The sequence of steps the browser takes to render a page.
