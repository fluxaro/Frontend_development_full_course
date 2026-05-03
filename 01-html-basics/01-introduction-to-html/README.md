# 01 — Introduction to HTML

## What is HTML?

**HTML** stands for **HyperText Markup Language**. It is the standard language used to create and structure content on the web.

- **HyperText** means text that contains links to other texts (hyperlinks).
- **Markup Language** means you use special tags to annotate (mark up) content, telling the browser what each piece of content *is*.

HTML is **not** a programming language — it doesn't have logic, loops, or variables. It's a *description* language. You describe the structure and meaning of your content, and the browser renders it visually.

---

## The Skeleton Analogy

> 🦴 **HTML is the skeleton of a webpage.**

Just like a skeleton gives a body its structure and shape, HTML gives a webpage its structure. CSS is the skin and clothes (appearance), and JavaScript is the muscles (behavior). Without HTML, there's nothing to style or interact with.

---

## Why HTML is the Foundation of the Web

Every single webpage you've ever visited — Google, YouTube, Wikipedia — is built on HTML. When your browser loads a page, it receives an HTML file and uses it to know:

- What headings to display
- Where paragraphs of text go
- Which images to show
- Where links point to

---

## Tags, Elements, and Attributes

### Tags
Tags are the building blocks of HTML. They are written with angle brackets:

```html
<tagname>content goes here</tagname>
```

Most tags come in **pairs**: an opening tag and a closing tag (with a `/`).

### Elements
An **element** is the complete unit: opening tag + content + closing tag.

```html
<p>This is a paragraph element.</p>
```

### Self-Closing Tags
Some elements don't wrap content — they stand alone:

```html
<img src="photo.jpg" alt="A photo">
<br>
<hr>
<input type="text">
```

### Attributes
Attributes provide **extra information** about an element. They go inside the opening tag:

```html
<a href="https://google.com" target="_blank">Visit Google</a>
```

- `href` is the attribute name
- `"https://google.com"` is the attribute value
- An element can have multiple attributes

---

## How a Browser Reads HTML

1. You type a URL or open an HTML file
2. The browser downloads the HTML file
3. The browser **parses** (reads) the HTML from top to bottom
4. It builds a **DOM** (Document Object Model) — a tree of all the elements
5. It renders (draws) the page on screen based on that tree

The browser is very forgiving — it will try to display something even if your HTML has mistakes. But writing correct HTML leads to better, more predictable results.

---

## Your First HTML File

Here's the simplest complete HTML page:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First Page</title>
  </head>
  <body>
    <h1>Hello, World!</h1>
    <p>This is my first webpage.</p>
  </body>
</html>
```

| Part | Purpose |
|------|---------|
| `<!DOCTYPE html>` | Tells the browser this is HTML5 |
| `<html>` | The root element wrapping everything |
| `<head>` | Metadata — info about the page (not visible) |
| `<body>` | The visible content of the page |

---

## What You'll Learn in This Module

By the end of `01-html-basics`, you will be able to:

- Build complete, well-structured HTML pages from scratch
- Use all common HTML elements correctly
- Write accessible, semantic HTML
- Understand how HTML, CSS, and JavaScript work together

Let's get started! 🚀
