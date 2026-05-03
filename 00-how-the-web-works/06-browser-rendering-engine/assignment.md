# Assignment — Browser Rendering Pipeline Page

## What You Are Building

Create an HTML page called `browser-rendering-explainer.html` that teaches the browser rendering pipeline to a complete beginner.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### 1. Introduction Section
An `<h1>` and a `<p>` explaining what the Critical Rendering Path is and why it matters.

### 2. The 6 Steps
For each step, create a `<section>` with:
- `<h2>` with the step name and number
- `<p>` explaining what happens in plain language
- A real-world analogy comparing it to something non-technical
- A `<pre>` block showing a code or tree structure example where relevant

### 3. Performance Impact Table
A `<table>` with columns: CSS Property | Triggers Layout? | Triggers Paint? | Triggers Composite?

Include at least 8 CSS properties (width, height, color, background, transform, opacity, top, left).

### 4. Key Terms Glossary
A `<dl>` defining: DOM, CSSOM, Render Tree, Layout, Paint, Composite, Render-blocking, Critical Rendering Path.

### 5. Developer Tips Section
An `<h2>` called "Tips for Faster Rendering" with an `<ol>` of at least 5 practical tips.

---

## What Good Looks Like

- Each step is explained clearly enough that a non-developer could understand it
- The performance table is accurate
- The page uses proper semantic HTML (sections, articles, dl, table with thead/tbody)
- The page passes W3C validation

---

## Submission

Save as `browser-rendering-explainer.html` and submit via GitHub.
