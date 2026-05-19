# Class Work — Typography Plugin Article

## What You Will Build

A styled blog article using the `@tailwindcss/typography` plugin loaded via CDN. You will see how `prose` transforms plain HTML into beautiful typographic content with zero custom CSS.

**Time:** 30 minutes  
**Output:** `article-with-prose.html`

---

## Step 1 — Setup with Typography Plugin via CDN

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Article with Prose</title>
  <!-- Load Tailwind + typography plugin via CDN -->
  <script src="https://cdn.tailwindcss.com?plugins=typography"></script>
</head>
<body class="bg-gray-50 font-sans">

</body>
</html>
```

**Key:** The `?plugins=typography` query string loads the typography plugin alongside Tailwind.

---

## Step 2 — Add the Page Layout

Inside `<body>`:

```html
<!-- Navbar -->
<nav class="bg-white border-b border-gray-200 sticky top-0 z-50">
  <div class="max-w-4xl mx-auto px-4 h-14 flex items-center justify-between">
    <span class="font-bold text-gray-900">DevBlog</span>
    <div class="flex gap-4 text-sm text-gray-500">
      <a href="#" class="hover:text-gray-900">Articles</a>
      <a href="#" class="hover:text-gray-900">About</a>
    </div>
  </div>
</nav>

<!-- Article wrapper -->
<main class="max-w-3xl mx-auto px-4 py-12">
  <!-- article goes here -->
</main>
```

---

## Step 3 — Add the Article WITHOUT prose

First, add the article without the `prose` class so you can see the unstyled HTML:

```html
<article>
  <h1>Understanding JavaScript Closures</h1>
  <p>Published May 11, 2026 · 8 min read</p>

  <p>A closure is one of the most powerful and often misunderstood concepts in JavaScript. At its core, a closure is a function that remembers the variables from its outer scope even after that outer function has finished executing.</p>

  <h2>What is a Closure?</h2>
  <p>When a function is created in JavaScript, it forms a closure over the variables in its surrounding scope. This means the inner function has access to:</p>
  <ul>
    <li>Its own local variables</li>
    <li>Variables from the outer function's scope</li>
    <li>Global variables</li>
  </ul>

  <h2>A Simple Example</h2>
  <p>Here is the classic counter example that demonstrates closures:</p>
  <pre><code>function makeCounter() {
  let count = 0;
  return function() {
    count++;
    return count;
  };
}

const counter = makeCounter();
console.log(counter()); // 1
console.log(counter()); // 2</code></pre>

  <blockquote>
    Closures are not a special syntax — they are a natural consequence of how JavaScript handles scope and function creation.
  </blockquote>

  <h2>Practical Uses</h2>
  <ol>
    <li>Data privacy and encapsulation</li>
    <li>Factory functions</li>
    <li>Event handlers that remember state</li>
    <li>Partial application and currying</li>
  </ol>
</article>
```

Open in browser — it looks like plain, unstyled HTML.

---

## Step 4 — Add the `prose` Class

Now add `prose prose-lg mx-auto` to the `<article>` tag:

```html
<article class="prose prose-lg mx-auto">
```

Reload the browser. The article now has:
- Beautiful heading hierarchy
- Comfortable paragraph spacing
- Styled lists with proper indentation
- A styled blockquote with a left border
- Monospace code blocks with background

**Zero custom CSS written.**

---

## Step 5 — Try Prose Variants

Change the class to see different sizes:

```html
<article class="prose prose-sm mx-auto">   <!-- smaller -->
<article class="prose prose-xl mx-auto">   <!-- larger -->
```

---

## Step 6 — Dark Mode Version

Add a dark section below the article:

```html
<section class="bg-gray-900 mt-12 -mx-4 px-4 py-12">
  <article class="prose prose-invert prose-lg mx-auto">
    <h2>Dark Mode Prose</h2>
    <p>The <code>prose-invert</code> class switches all prose colors to work on dark backgrounds. The same content, automatically adapted for dark mode.</p>
    <blockquote>prose-invert makes all text colors light automatically.</blockquote>
  </article>
</section>
```

---

## Checklist

- [ ] CDN loads with `?plugins=typography`
- [ ] Article without `prose` looks unstyled
- [ ] Adding `prose prose-lg` transforms the article
- [ ] Headings, lists, blockquote, and code blocks all look styled
- [ ] `prose-invert` works on the dark section
- [ ] No custom CSS written anywhere

---

## Bonus Challenges

1. Add `prose-blue` to change the link and heading accent color
2. Add a `<table>` inside the prose and see how it gets styled automatically
3. Try `prose-gray`, `prose-slate`, `prose-zinc` for different color schemes
