# 02 — CSS Combinators: Descendant, Child, Sibling

## What Is This Lesson About?

Combinators let you select elements based on their relationship to other elements in the HTML tree. Instead of adding classes to every element, you can target elements by where they live in the document.

---

## The Four Combinators

### 1. Descendant Combinator (space)

Selects all matching elements that are descendants (children, grandchildren, etc.) of the first element.

```css
/* All <a> tags inside <nav> */
nav a {
  color: white;
  text-decoration: none;
}

/* All <p> tags inside <article> */
article p {
  line-height: 1.8;
}
```

```html
<nav>
  <a href="/">Home</a>  <!-- ✅ selected -->
  <ul>
    <li><a href="/about">About</a></li>  <!-- ✅ selected (grandchild) -->
  </ul>
</nav>
```

---

### 2. Child Combinator `>`

Selects only direct children — not grandchildren.

```css
/* Only direct <li> children of <ul> */
ul > li {
  list-style: none;
  padding: 8px 0;
}

/* Only direct <p> children of .card */
.card > p {
  color: #666;
}
```

```html
<ul>
  <li>Direct child ✅</li>
  <li>Direct child ✅
    <ul>
      <li>Grandchild ❌ (not selected)</li>
    </ul>
  </li>
</ul>
```

---

### 3. Adjacent Sibling Combinator `+`

Selects the element immediately after the first element (same parent).

```css
/* The <p> immediately after an <h2> */
h2 + p {
  font-size: 1.1rem;
  color: #555;
  margin-top: 0;
}

/* The <label> immediately after a <input> */
input + label {
  margin-left: 8px;
}
```

```html
<h2>Section Title</h2>
<p>This paragraph is selected ✅</p>
<p>This one is NOT selected ❌</p>
```

---

### 4. General Sibling Combinator `~`

Selects all matching siblings after the first element.

```css
/* All <p> elements after an <h2> (same parent) */
h2 ~ p {
  color: #555;
}
```

```html
<h2>Title</h2>
<p>Selected ✅</p>
<p>Selected ✅</p>
<p>Selected ✅</p>
```

---

## Comparison Table

| Combinator | Syntax | Selects |
|---|---|---|
| Descendant | `A B` | All B inside A (any depth) |
| Child | `A > B` | Direct B children of A only |
| Adjacent sibling | `A + B` | B immediately after A |
| General sibling | `A ~ B` | All B after A (same parent) |

---

## Real-World Examples

```css
/* Style all links in the navigation */
nav a { color: white; }

/* Style only direct list items in the main nav */
nav > ul > li { display: inline-block; }

/* Remove top margin from first paragraph after a heading */
h2 + p { margin-top: 0; }

/* Style all paragraphs after a blockquote */
blockquote ~ p { font-style: italic; }

/* Style form labels that follow inputs */
input:checked + label { font-weight: bold; }
```
