# 04 — Text Formatting Elements

## Why Text Formatting Matters

HTML provides many elements for formatting text. The key principle: **use elements for their semantic meaning, not their visual appearance**. Use CSS for visual styling.

For example, `<strong>` means "this text is important" — it happens to appear bold by default. But if you just want bold text for visual reasons, use CSS `font-weight: bold` instead.

---

## Headings: `<h1>` through `<h6>`

```html
<h1>Main Page Title</h1>
<h2>Major Section</h2>
<h3>Subsection</h3>
<h4>Sub-subsection</h4>
<h5>Rarely used</h5>
<h6>Rarely used</h6>
```

**Rules:**
- Only **one `<h1>`** per page (the main title)
- Don't skip levels (don't go from h1 to h4)
- Use headings for structure, not for making text big

---

## Paragraphs: `<p>`

```html
<p>This is a paragraph. The browser adds space above and below automatically.</p>
<p>This is another paragraph. Each <p> starts on a new line.</p>
```

---

## Emphasis and Importance

### `<strong>` — Important text (bold by default)
```html
<p>Please <strong>do not</strong> share your password with anyone.</p>
```
Semantic meaning: **strong importance**. Screen readers may emphasize this.

### `<em>` — Emphasized text (italic by default)
```html
<p>I <em>really</em> love learning HTML.</p>
```
Semantic meaning: **stress emphasis** — changes the meaning of the sentence.

### `<b>` — Bold without semantic meaning
```html
<p>The <b>product name</b> is listed in the catalog.</p>
```
Use when you want bold for stylistic reasons, not importance.

### `<i>` — Italic without semantic meaning
```html
<p>The term <i>HTML</i> stands for HyperText Markup Language.</p>
<p>She thought, <i>this is going to be a long day.</i></p>
```
Use for technical terms, foreign words, thoughts, titles.

---

## Highlighting and Marking

### `<mark>` — Highlighted text
```html
<p>Search results for "HTML": Learn <mark>HTML</mark> basics today.</p>
```
Like a yellow highlighter. Use for search result highlights or important passages.

### `<del>` — Deleted/strikethrough text
```html
<p>Price: <del>$99</del> <ins>$49</ins> — 50% off!</p>
```
Represents text that has been removed or is no longer accurate.

### `<ins>` — Inserted text (underlined by default)
```html
<p>The meeting is on <del>Monday</del> <ins>Tuesday</ins>.</p>
```
Represents text that has been added or inserted.

---

## Superscript and Subscript

### `<sup>` — Superscript
```html
<p>E = mc<sup>2</sup></p>
<p>The 1<sup>st</sup> place winner is...</p>
<p>Visit our website<sup>[1]</sup></p>
```

### `<sub>` — Subscript
```html
<p>Water is H<sub>2</sub>O</p>
<p>CO<sub>2</sub> is carbon dioxide</p>
```

---

## Quotations

### `<blockquote>` — Long quotation (block-level)
```html
<blockquote cite="https://source.com">
  <p>The only way to do great work is to love what you do.</p>
  <footer>— Steve Jobs</footer>
</blockquote>
```

### `<q>` — Short inline quotation
```html
<p>As Einstein said, <q>Imagination is more important than knowledge.</q></p>
```
Browsers automatically add quotation marks around `<q>` content.

### `<cite>` — Citation/reference
```html
<p>According to <cite>MDN Web Docs</cite>, the img element is void.</p>
```

---

## Code and Technical Text

### `<code>` — Inline code
```html
<p>Use the <code>console.log()</code> function to debug JavaScript.</p>
<p>The <code>&lt;p&gt;</code> tag creates a paragraph.</p>
```

### `<pre>` — Preformatted text (preserves whitespace)
```html
<pre>
function greet(name) {
  return "Hello, " + name + "!";
}
</pre>
```
Preserves spaces, tabs, and line breaks exactly as written.

### `<pre><code>` — Code block (best practice)
```html
<pre><code>
const greeting = "Hello, World!";
console.log(greeting);
</code></pre>
```

### `<kbd>` — Keyboard input
```html
<p>Press <kbd>Ctrl</kbd> + <kbd>S</kbd> to save.</p>
```

### `<samp>` — Sample output
```html
<p>The program outputs: <samp>Hello, World!</samp></p>
```

### `<var>` — Variable
```html
<p>The formula is: <var>E</var> = <var>m</var><var>c</var><sup>2</sup></p>
```

---

## Other Useful Elements

### `<abbr>` — Abbreviation
```html
<p><abbr title="HyperText Markup Language">HTML</abbr> is the language of the web.</p>
```
Hovering shows the full form as a tooltip.

### `<time>` — Date/time
```html
<p>Published on <time datetime="2025-01-15">January 15, 2025</time></p>
<p>The event starts at <time datetime="19:00">7 PM</time></p>
```

### `<address>` — Contact information
```html
<address>
  Written by <a href="mailto:jane@example.com">Jane Smith</a><br>
  123 Main Street<br>
  New York, NY 10001
</address>
```

### `<small>` — Fine print
```html
<p><small>© 2025 Frontend Bootcamp. All rights reserved.</small></p>
```

### `<hr>` — Thematic break (horizontal rule)
```html
<p>End of section one.</p>
<hr>
<p>Start of section two.</p>
```

### `<br>` — Line break
```html
<p>123 Main Street<br>
New York, NY 10001</p>
```
Use sparingly — for addresses and poetry, not for spacing between paragraphs.

---

## Semantic vs Presentational

| Semantic (use these) | Presentational (avoid) | Why |
|---------------------|----------------------|-----|
| `<strong>` | `<b>` for importance | `<strong>` has meaning |
| `<em>` | `<i>` for emphasis | `<em>` has meaning |
| `<del>` | CSS `text-decoration: line-through` | `<del>` has semantic meaning |
| `<mark>` | CSS `background: yellow` | `<mark>` has semantic meaning |

**Rule of thumb:** If you're choosing an element because of how it *looks*, use CSS instead. If you're choosing it because of what it *means*, use the HTML element.
