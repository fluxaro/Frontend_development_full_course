# Notes — Text Formatting Elements

## All Text Elements Cheat Sheet

### Headings
```html
<h1>Page Title — one per page</h1>
<h2>Major Section</h2>
<h3>Subsection</h3>
<h4>Sub-subsection</h4>
<h5>Rarely used</h5>
<h6>Rarely used</h6>
```

### Text Content
```html
<p>Paragraph</p>
<br>                    <!-- Line break (use sparingly) -->
<hr>                    <!-- Thematic break / horizontal rule -->
```

### Emphasis & Importance
```html
<strong>Important text</strong>          <!-- Bold + semantic importance -->
<em>Emphasized text</em>                 <!-- Italic + semantic emphasis -->
<b>Bold (no semantic meaning)</b>        <!-- Visual bold only -->
<i>Italic (no semantic meaning)</i>      <!-- Visual italic, technical terms -->
<u>Underline (avoid — looks like link)</u>
```

### Marking & Editing
```html
<mark>Highlighted text</mark>            <!-- Like a highlighter -->
<del>Deleted/removed text</del>          <!-- Strikethrough, removed content -->
<ins>Inserted/added text</ins>           <!-- Underline, added content -->
<s>Strikethrough (no longer accurate)</s>
```

### Superscript & Subscript
```html
E = mc<sup>2</sup>                       <!-- Superscript -->
H<sub>2</sub>O                           <!-- Subscript -->
```

### Quotations
```html
<blockquote cite="url">Long quote</blockquote>   <!-- Block quote -->
<q>Short inline quote</q>                         <!-- Inline quote (adds "" automatically) -->
<cite>Source title</cite>                         <!-- Citation/reference -->
```

### Code & Technical
```html
<code>inline code</code>                 <!-- Inline code snippet -->
<pre>preformatted text</pre>             <!-- Preserves whitespace/newlines -->
<pre><code>code block</code></pre>       <!-- Multi-line code block -->
<kbd>Ctrl+S</kbd>                        <!-- Keyboard input -->
<samp>output text</samp>                 <!-- Sample program output -->
<var>variable</var>                      <!-- Mathematical/programming variable -->
```

### Semantic Inline Elements
```html
<abbr title="Full Form">Abbr</abbr>      <!-- Abbreviation with tooltip -->
<time datetime="2025-01-15">Jan 15</time> <!-- Date/time -->
<small>Fine print, copyright</small>     <!-- Small/fine print -->
<address>Contact info</address>          <!-- Contact information -->
```

---

## Semantic vs Presentational Elements

| Use This | Not This | Reason |
|----------|----------|--------|
| `<strong>` | `<b>` | When text is genuinely important |
| `<em>` | `<i>` | When text needs stress emphasis |
| `<del>` | CSS `text-decoration: line-through` | When content was actually removed |
| `<ins>` | CSS `text-decoration: underline` | When content was actually added |
| `<mark>` | CSS `background: yellow` | When content is highlighted for relevance |
| CSS `font-weight: bold` | `<b>` | When you just want visual bold |
| CSS `font-style: italic` | `<i>` | When you just want visual italic |

**The rule:** If you're choosing an element for how it *looks*, use CSS. If you're choosing it for what it *means*, use the HTML element.

---

## `<time>` datetime Formats

```html
<!-- Date -->
<time datetime="2025-01-15">January 15, 2025</time>

<!-- Time -->
<time datetime="14:30">2:30 PM</time>

<!-- Date and time -->
<time datetime="2025-01-15T14:30:00">Jan 15 at 2:30 PM</time>

<!-- Duration (ISO 8601) -->
<time datetime="PT2H30M">2 hours 30 minutes</time>
<time datetime="P3D">3 days</time>

<!-- Year and month -->
<time datetime="2025-01">January 2025</time>
```

---

## `<abbr>` Best Practices

```html
<!-- First use: spell it out with abbr -->
<p><abbr title="HyperText Markup Language">HTML</abbr> is the language of the web.</p>

<!-- Subsequent uses: just use the abbreviation -->
<p>HTML is easy to learn.</p>
```

---

## Heading Hierarchy Rules

```
✅ Correct:
h1 → h2 → h3 → h4

❌ Wrong (skipping levels):
h1 → h3 (skipped h2)
h2 → h5 (skipped h3, h4)

❌ Wrong (multiple h1):
h1 "Main Title"
h1 "Another Main Title"  ← only one h1 per page!
```

---

## Common Mistakes

### ❌ Using `<br>` for paragraph spacing
```html
<!-- Wrong -->
<p>First paragraph.</p>
<br>
<br>
<p>Second paragraph.</p>

<!-- Correct — use CSS margin instead -->
<p>First paragraph.</p>
<p>Second paragraph.</p>
/* CSS: p { margin-bottom: 1.5em; } */
```

### ❌ Using headings for font size
```html
<!-- Wrong — using h3 just to make text bigger -->
<h3>This text isn't actually a heading</h3>

<!-- Correct — use CSS for size -->
<p style="font-size: 1.2rem; font-weight: bold;">Bigger text</p>
```

### ❌ Nesting block elements in inline elements
```html
<!-- Wrong — p is block, can't go inside span (inline) -->
<span><p>Text</p></span>

<!-- Correct -->
<div><p>Text</p></div>
```

### ❌ Empty paragraphs for spacing
```html
<!-- Wrong -->
<p>Content</p>
<p></p>  <!-- empty paragraph for spacing -->
<p>More content</p>

<!-- Correct — use CSS margin/padding -->
<p>Content</p>
<p>More content</p>
/* CSS: p { margin-bottom: 24px; } */
```

### ❌ Forgetting `datetime` on `<time>`
```html
<!-- Works but loses machine-readable value -->
<time>January 15, 2025</time>

<!-- Better — machine-readable datetime -->
<time datetime="2025-01-15">January 15, 2025</time>
```

---

## Block vs Inline Elements

**Block elements** — start on a new line, take full width:
`<h1>`-`<h6>`, `<p>`, `<blockquote>`, `<pre>`, `<address>`, `<hr>`

**Inline elements** — flow within text, only as wide as content:
`<strong>`, `<em>`, `<mark>`, `<del>`, `<ins>`, `<code>`, `<abbr>`, `<time>`, `<small>`, `<sup>`, `<sub>`, `<q>`, `<cite>`, `<kbd>`, `<b>`, `<i>`, `<u>`, `<s>`
