# Class Work — Blog Post with Text Formatting

## What You Will Build

A blog post page formatted using all major HTML text elements. You will format a recipe article using headings, paragraphs, bold, italic, code, blockquotes, and more.

**Time:** 40 minutes  
**Output:** A fully formatted blog post that reads like a real article

---

## The Article: Classic Chocolate Chip Cookies

You will format this content using proper HTML text elements. Follow each step.

---

## Step 1 — Set Up the Page

Create a new file called `cookie-recipe.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Classic Chocolate Chip Cookies Recipe</title>
  </head>
  <body>

  </body>
</html>
```

---

## Step 2 — Add the Main Heading

Inside `<body>`, add:

```html
<h1>Classic Chocolate Chip Cookies</h1>
```

Only one `<h1>` per page — this is the article title.

---

## Step 3 — Add Publication Info

```html
<p>
  <small>Published on <time datetime="2025-01-15">January 15, 2025</time> by
  <strong>Chef Maria Santos</strong></small>
</p>
```

**What each element does:**
- `<small>` — fine print, secondary information
- `<time datetime="...">` — machine-readable date with human-readable display text
- `<strong>` — important text (bold with semantic meaning)

---

## Step 4 — Add an Introduction Paragraph

```html
<p>
  There is nothing quite like a warm, freshly baked chocolate chip cookie.
  This recipe has been <em>perfected over 20 years</em> and produces cookies
  that are crispy on the outside, <strong>chewy in the middle</strong>, and
  absolutely irresistible.
</p>
```

**What each element does:**
- `<em>` — emphasized text (italic with semantic meaning)
- `<strong>` — important text (bold with semantic meaning)

---

## Step 5 — Add a Blockquote

```html
<blockquote>
  <p>"The secret to perfect cookies is not overmixing the dough —
  stop as soon as the flour disappears."</p>
  <footer>— Chef Maria Santos</footer>
</blockquote>
```

`<blockquote>` is for quoting someone else's words. Always include a source.

---

## Step 6 — Add the Ingredients Section

```html
<h2>Ingredients</h2>
<p>This recipe makes <strong>24 cookies</strong>.
Prep time: <time datetime="PT15M">15 minutes</time>.
Bake time: <time datetime="PT12M">12 minutes</time>.</p>

<h3>Dry Ingredients</h3>
<ul>
  <li>2 and one quarter cups all-purpose flour</li>
  <li>1 teaspoon baking soda</li>
  <li>1 teaspoon salt</li>
</ul>

<h3>Wet Ingredients</h3>
<ul>
  <li>1 cup butter, softened</li>
  <li>Three quarters cup granulated sugar</li>
  <li>Three quarters cup packed brown sugar</li>
  <li>2 large eggs</li>
  <li>2 teaspoons vanilla extract</li>
</ul>
```

---

## Step 7 — Add Instructions with del and ins

```html
<h2>Instructions</h2>

<p><strong>Step 1:</strong> Preheat your oven to
<del>350°F</del> <ins>375°F (190°C)</ins>.
Line baking sheets with parchment paper.</p>

<p><strong>Step 2:</strong> In a large bowl, beat butter and both sugars
until <em>light and fluffy</em>, about 3–4 minutes.
<mark>Do not skip this step</mark> — proper creaming is key to texture.</p>

<p><strong>Step 3:</strong> Add eggs one at a time, then vanilla.
Mix until combined.</p>

<p><strong>Step 4:</strong> Gradually add the flour mixture.
<strong>Stop mixing as soon as the flour disappears.</strong>
Overmixing makes cookies tough.</p>

<p><strong>Step 5:</strong> Bake for 9–11 minutes until edges are golden.
Centers will look underdone — that is correct. They firm up as they cool.</p>
```

**What each element does:**
- `<del>` — deleted/removed text (shown with strikethrough)
- `<ins>` — inserted/corrected text (shown with underline)
- `<mark>` — highlighted text, like a yellow marker

---

## Step 8 — Add a Code Example

```html
<h2>Baker's Formula</h2>

<p>
  Professional bakers use weight ratios. The formula for these cookies is:
  <code>butter:sugar:flour = 1:1.5:2.25</code> by weight.
</p>

<p>
  If you have a kitchen scale, use this formula:
</p>

<pre><code>Butter:  227g (1 cup)
Sugar:   300g (1.5 cups combined)
Flour:   281g (2.25 cups)
Eggs:    2 large
Vanilla: 10ml (2 tsp)</code></pre>
```

**What each element does:**
- `<code>` — inline code or technical notation
- `<pre>` — preformatted text that preserves whitespace and line breaks
- `<pre><code>` together — a block of code

---

## Step 9 — Add Superscript and Subscript

```html
<h2>Nutrition Per Cookie</h2>

<p>
  Calories: <strong>180 kcal</strong> ·
  Carbs: 24g ·
  Fat: 9g ·
  Protein: 2g
</p>

<p>
  <small>
    <sup>*</sup>Nutritional values are approximate.
    CO<sub>2</sub> footprint: approximately 0.3kg per batch.
  </small>
</p>
```

**What each element does:**
- `<sup>` — superscript (footnote markers, exponents like x²)
- `<sub>` — subscript (chemical formulas like H₂O, CO₂)

---

## Step 10 — Add Abbreviations and Address

```html
<h2>About This Recipe</h2>

<p>
  This recipe follows <abbr title="American Culinary Federation">ACF</abbr>
  standards for home baking. It has been tested in both
  <abbr title="United States">US</abbr> and metric measurements.
</p>

<address>
  Recipe questions? Contact us at
  <a href="mailto:recipes@example.com">recipes@example.com</a>
</address>
```

**What each element does:**
- `<abbr title="...">` — abbreviation with full text in the title attribute (shows on hover)
- `<address>` — contact information for the author or owner of the content

---

## Checklist

- [ ] `<h1>` for main title, `<h2>` for sections, `<h3>` for subsections
- [ ] `<strong>` used for important text
- [ ] `<em>` used for emphasized text
- [ ] `<mark>` used to highlight key info
- [ ] `<del>` and `<ins>` used for a correction
- [ ] `<blockquote>` for the quote with a source
- [ ] `<time>` with `datetime` attribute
- [ ] `<code>` for inline code
- [ ] `<pre><code>` for a code block
- [ ] `<sub>` and `<sup>` used correctly
- [ ] `<abbr>` with `title` attribute
- [ ] `<address>` for contact info
- [ ] `<small>` for fine print

---

## Bonus Challenges

1. Add a `<q>` inline quote somewhere in the text
2. Add `<cite>` around a book or source reference
3. Add a `<dfn>` element to define a technical term
4. Add a `<kbd>` element for a keyboard shortcut (e.g., "Press `Ctrl+Z` to undo")
