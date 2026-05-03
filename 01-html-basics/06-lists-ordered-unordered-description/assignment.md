# Assignment — Top 10 Programming Languages Page

## What You Are Building

Create an HTML page called `top-languages.html` that presents the top 10 programming languages using all three list types.

No CSS. No JavaScript. Pure HTML structure only.

---

## Requirements

### 1. Main Heading
An `<h1>` with the title "Top 10 Programming Languages in 2025".

### 2. Ranked List (Ordered)
An `<ol>` listing the top 10 programming languages in order of popularity. For each language, the `<li>` should include:
- The language name in `<strong>`
- A short description of what it is used for

### 3. Categories Section (Unordered with Nesting)
An `<h2>` called "Languages by Category" with a `<ul>` that groups languages into categories. Each category should be a `<li>` containing a nested `<ul>` of languages in that category.

Categories to include:
- Web Development (Frontend)
- Web Development (Backend)
- Data Science and AI
- Mobile Development
- Systems Programming

### 4. Description List Glossary
An `<h2>` called "Key Terms" with a `<dl>` defining at least 8 terms related to programming languages:
- Compiled language
- Interpreted language
- Statically typed
- Dynamically typed
- Object-oriented
- Functional programming
- Framework
- Library

### 5. Learning Order (Ordered)
An `<h2>` called "Recommended Learning Order for Web Developers" with an `<ol>` showing the recommended sequence.

---

## What Good Looks Like

- The ranked list is actually ranked (most popular first)
- The nested list is properly structured (no invalid nesting)
- The description list uses `<dt>` and `<dd>` correctly
- All content is real and accurate
- The page passes W3C validation

---

## Bonus Challenges

- Add a `reversed` attribute to one list to show a countdown
- Add `type="I"` to use Roman numerals on one ordered list
- Add a `<nav>` with anchor links to each section
- Add a `<table>` comparing 5 languages across: Year created, Creator, Typing, Main use

---

## Submission

Save as `top-languages.html` and submit via GitHub.
