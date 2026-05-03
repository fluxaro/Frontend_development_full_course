# 06 — Lists: Ordered, Unordered, and Description Lists

## What Is This Lesson About?

HTML has three types of lists, each for a different purpose. Lists are one of the most commonly used HTML elements — navigation menus, step-by-step instructions, ingredient lists, and definition glossaries all use lists.

---

## The Three Types of Lists

### 1. Unordered List `<ul>`

Use when the order does not matter. Items appear with bullet points by default.

```html
<ul>
  <li>HTML</li>
  <li>CSS</li>
  <li>JavaScript</li>
</ul>
```

**Real-world uses:** Ingredient lists, feature lists, navigation menus, tag lists.

### 2. Ordered List `<ol>`

Use when the order matters. Items appear numbered by default.

```html
<ol>
  <li>Boil water</li>
  <li>Add pasta</li>
  <li>Cook for 10 minutes</li>
  <li>Drain and serve</li>
</ol>
```

**Real-world uses:** Step-by-step instructions, rankings, procedures, numbered tutorials.

**Attributes:**
- `start="5"` — start numbering from 5
- `reversed` — count down instead of up
- `type="A"` — use letters (A, B, C) instead of numbers

### 3. Description List `<dl>`

Use for term-definition pairs. Like a glossary or dictionary.

```html
<dl>
  <dt>HTML</dt>
  <dd>HyperText Markup Language — the structure of web pages.</dd>

  <dt>CSS</dt>
  <dd>Cascading Style Sheets — the styling of web pages.</dd>
</dl>
```

- `<dl>` — the description list container
- `<dt>` — description term (the word being defined)
- `<dd>` — description details (the definition)

**Real-world uses:** Glossaries, FAQs, metadata displays, key-value pairs.

---

## Nested Lists

You can put a list inside another list item:

```html
<ul>
  <li>Frontend
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>JavaScript</li>
    </ul>
  </li>
  <li>Backend
    <ul>
      <li>Node.js</li>
      <li>Python</li>
    </ul>
  </li>
</ul>
```

---

## Navigation Menus Use Lists

Navigation menus are semantically built with unordered lists:

```html
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>
```

CSS then removes the bullets and makes them horizontal. The HTML structure is still a list.

---

## When to Use Each

| Situation | List Type |
|---|---|
| Navigation menu | `<ul>` |
| Ingredients | `<ul>` |
| Features list | `<ul>` |
| Step-by-step instructions | `<ol>` |
| Top 10 ranking | `<ol>` |
| Recipe steps | `<ol>` |
| Glossary | `<dl>` |
| FAQ | `<dl>` |
| Key-value metadata | `<dl>` |
