# Class Work — Style a Blog Post with Typography

## What You Will Build

A beautifully typeset blog post using Google Fonts and all text styling properties.

**Time:** 35 minutes

---

## Step 1 — Load Google Fonts

Create `typography-demo.html`:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Typography Demo</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700&family=Inter:wght@400;500;600&display=swap" rel="stylesheet">
  <link rel="stylesheet" href="typography.css">
</head>
<body>

  <article class="blog-post">

    <header class="post-header">
      <span class="category">Web Development</span>
      <h1>The Art of Web Typography</h1>
      <p class="lead">Good typography is invisible. Bad typography is everywhere. Learn how to make your text beautiful and readable.</p>
      <div class="meta">
        <span>By <strong>Alex Johnson</strong></span>
        <span>January 15, 2025</span>
        <span>8 min read</span>
      </div>
    </header>

    <section>
      <h2>Why Typography Matters</h2>
      <p>Typography is the art of arranging type to make written language legible, readable, and appealing. On the web, good typography can mean the difference between a user reading your content or bouncing immediately.</p>
      <p>Studies show that users form an opinion about a website within <strong>50 milliseconds</strong>. Typography plays a huge role in that first impression.</p>
    </section>

    <section>
      <h2>The Type Scale</h2>
      <p>A type scale is a set of font sizes that work harmoniously together. Here are the sizes in this design system:</p>
      <div class="type-scale">
        <p class="size-xs">Extra Small — 0.75rem (12px)</p>
        <p class="size-sm">Small — 0.875rem (14px)</p>
        <p class="size-base">Base — 1rem (16px)</p>
        <p class="size-lg">Large — 1.125rem (18px)</p>
        <p class="size-xl">Extra Large — 1.25rem (20px)</p>
        <p class="size-2xl">2XL — 1.5rem (24px)</p>
        <p class="size-3xl">3XL — 1.875rem (30px)</p>
      </div>
    </section>

    <blockquote>
      <p>"Typography is what language looks like."</p>
      <footer>— Ellen Lupton, <cite>Thinking with Type</cite></footer>
    </blockquote>

    <section>
      <h2>Text Styling Properties</h2>
      <p>Here are some common text styling examples:</p>
      <ul>
        <li><span class="uppercase">uppercase text</span></li>
        <li><span class="lowercase">LOWERCASE TEXT</span></li>
        <li><span class="capitalize">capitalize each word</span></li>
        <li><span class="tracking-wide">wide letter spacing</span></li>
        <li><span class="truncate-demo">This text is very long and will be truncated with an ellipsis when it overflows its container</span></li>
      </ul>
    </section>

    <section>
      <h2>Code Typography</h2>
      <p>Use <code>font-family: monospace</code> for inline code. For code blocks, use <code>pre</code> with <code>code</code>:</p>
      <pre><code>body {
  font-family: 'Inter', system-ui, sans-serif;
  font-size: 1rem;
  line-height: 1.6;
  color: #333;
}</code></pre>
    </section>

  </article>

</body>
</html>
```

---

## Step 2 — Create the CSS

Create `typography.css`:

```css
:root {
  --font-heading: 'Playfair Display', Georgia, serif;
  --font-body: 'Inter', system-ui, sans-serif;
  --font-mono: 'Courier New', monospace;

  --text-xs:   0.75rem;
  --text-sm:   0.875rem;
  --text-base: 1rem;
  --text-lg:   1.125rem;
  --text-xl:   1.25rem;
  --text-2xl:  1.5rem;
  --text-3xl:  1.875rem;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }

body {
  font-family: var(--font-body);
  font-size: var(--text-base);
  line-height: 1.7;
  color: #1a1a2e;
  background: #fafafa;
}

.blog-post {
  max-width: 65ch;
  margin: 4rem auto;
  padding: 0 1.5rem;
}

.post-header { margin-bottom: 3rem; }

.category {
  font-size: var(--text-xs);
  font-weight: 600;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  color: #3498db;
}

h1 {
  font-family: var(--font-heading);
  font-size: var(--text-3xl);
  line-height: 1.2;
  margin: 0.5rem 0 1rem;
  color: #1a1a2e;
}

h2 {
  font-family: var(--font-heading);
  font-size: var(--text-2xl);
  line-height: 1.3;
  margin: 2.5rem 0 1rem;
  color: #1a1a2e;
}

.lead {
  font-size: var(--text-lg);
  color: #555;
  line-height: 1.6;
  margin-bottom: 1rem;
}

.meta {
  font-size: var(--text-sm);
  color: #888;
  display: flex;
  gap: 1rem;
}

p { margin-bottom: 1.25rem; }

blockquote {
  border-left: 4px solid #3498db;
  padding: 1rem 1.5rem;
  margin: 2rem 0;
  background: #f0f7ff;
  border-radius: 0 8px 8px 0;
}

blockquote p {
  font-family: var(--font-heading);
  font-size: var(--text-xl);
  font-style: italic;
  color: #2c3e50;
  margin-bottom: 0.5rem;
}

blockquote footer {
  font-size: var(--text-sm);
  color: #888;
}

/* Type scale demo */
.size-xs   { font-size: var(--text-xs); }
.size-sm   { font-size: var(--text-sm); }
.size-base { font-size: var(--text-base); }
.size-lg   { font-size: var(--text-lg); }
.size-xl   { font-size: var(--text-xl); }
.size-2xl  { font-size: var(--text-2xl); }
.size-3xl  { font-size: var(--text-3xl); }

/* Text transforms */
.uppercase { text-transform: uppercase; letter-spacing: 0.05em; }
.lowercase { text-transform: lowercase; }
.capitalize { text-transform: capitalize; }
.tracking-wide { letter-spacing: 0.15em; }

/* Truncation */
.truncate-demo {
  display: block;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
  max-width: 300px;
}

/* Code */
code {
  font-family: var(--font-mono);
  font-size: 0.875em;
  background: #f0f0f0;
  padding: 2px 6px;
  border-radius: 4px;
  color: #e74c3c;
}

pre {
  background: #1e1e2e;
  color: #cdd6f4;
  padding: 1.5rem;
  border-radius: 8px;
  overflow-x: auto;
  margin: 1.5rem 0;
}

pre code {
  background: none;
  padding: 0;
  color: inherit;
  font-size: 0.9rem;
}
```

---

## Checklist

- [ ] Google Fonts loaded with `preconnect`
- [ ] Heading font and body font are different
- [ ] Type scale defined as CSS custom properties
- [ ] `max-width: 65ch` for readable line length
- [ ] `line-height: 1.7` for body text
- [ ] Blockquote styled with border-left
- [ ] Code styled with monospace font
- [ ] Text transform examples shown
- [ ] Truncation with ellipsis works
