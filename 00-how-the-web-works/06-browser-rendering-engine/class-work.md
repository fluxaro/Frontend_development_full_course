# Class Work — Observe the Browser Rendering Pipeline

## What You Will Do

Use Chrome DevTools to observe the rendering pipeline in action, then build an HTML page that explains each step.

**Time:** 35 minutes

---

## Activity 1: Record a Page Load in DevTools (15 minutes)

### Step 1 — Open DevTools Performance Tab

Open Chrome. Press `F12` (Windows) or `Cmd+Option+I` (Mac). Click the **Performance** tab.

### Step 2 — Record a Page Load

1. Click the circular record button (or press `Ctrl+Shift+E`)
2. Type `https://example.com` in the address bar and press Enter
3. Wait for the page to fully load
4. Click Stop in the Performance panel

### Step 3 — Analyze the Flame Chart

Look at the flame chart that appears. Find and identify these events:

| Event to Find | Color in DevTools | What It Means |
|---|---|---|
| Parse HTML | Blue | Browser reading HTML and building DOM |
| Recalculate Style | Purple | Browser computing CSS styles |
| Layout | Purple | Browser calculating positions |
| Paint | Green | Browser drawing pixels |
| Composite Layers | Green | Browser combining layers |

Write down:
- How long did Parse HTML take?
- How long did the first Layout take?
- How long did the first Paint take?
- What was the total scripting time?

### Step 4 — Check the Network Tab

Switch to the **Network** tab. Reload the page. Look at the waterfall chart.

Find:
- Which resource loaded first?
- Were any resources render-blocking? (Look for resources that delay the first paint)
- What was the Time to First Byte (TTFB)?

---

## Activity 2: Build a Rendering Pipeline Explainer Page (20 minutes)

Create a file called `rendering-pipeline.html`.

Using only HTML, build a page that explains the 6 steps of the browser rendering pipeline. For each step, include:
- An `<h2>` with the step name
- A `<p>` explaining what happens in plain language
- A `<pre>` block showing a simple code example where relevant

The 6 steps:
1. Parse HTML → Build DOM
2. Parse CSS → Build CSSOM
3. Combine → Render Tree
4. Layout (calculate positions)
5. Paint (draw pixels)
6. Composite (combine layers)

Also include a `<table>` comparing which CSS properties trigger Layout vs Paint vs Composite only.

---

## Checklist

- [ ] Recorded a page load in Performance tab
- [ ] Identified Parse HTML, Layout, and Paint events
- [ ] Built `rendering-pipeline.html` with all 6 steps
- [ ] Table comparing CSS property costs is included
