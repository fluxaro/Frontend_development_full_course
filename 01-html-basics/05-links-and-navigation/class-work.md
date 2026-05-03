# Class Work — Navigation and Links

## What You Will Build

A single-page site with a navigation bar that links to 4 sections on the same page. You will use every type of link: anchor links, external links, email links, phone links, and download links.

**Time:** 40 minutes  
**Output:** A working single-page portfolio with full navigation

---

## Step 1 — Set Up the Page Structure

Create a new file called `portfolio-nav.html`:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Portfolio — Navigation Demo</title>
  </head>
  <body>

  </body>
</html>
```

---

## Step 2 — Build the Navigation Bar

Add this inside `<body>`, before the sections:

```html
<header>
  <nav>
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#projects">Projects</a></li>
      <li><a href="#contact">Contact</a></li>
      <li><a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a></li>
    </ul>
  </nav>
</header>
```

**What each part does:**
- `<nav>` — semantic element for navigation links
- `<ul>` and `<li>` — proper list structure for navigation items
- `href="#home"` — anchor link that jumps to the element with `id="home"`
- `target="_blank"` — opens the link in a new tab
- `rel="noopener noreferrer"` — security attribute required when using `target="_blank"`

---

## Step 3 — Add the Home Section

```html
<main>
  <section id="home">
    <h1>Hi, I am Alex Rivera</h1>
    <p>Frontend developer in training. I build things for the web.</p>
    <a href="#about">Learn More About Me</a>
  </section>
```

**Key point:** The `id="home"` on the `<section>` is what makes `href="#home"` in the nav work. They must match exactly.

---

## Step 4 — Add the About Section

```html
  <section id="about">
    <h2>About Me</h2>
    <p>
      I am a frontend developer learning HTML, CSS, and JavaScript.
      I love building clean, accessible websites that work for everyone.
    </p>
    <p>
      When I am not coding, I enjoy hiking, photography, and reading about
      technology and design.
    </p>
    <p>
      Want to see my full background?
      <a href="resume.html">View my resume</a>.
    </p>
  </section>
```

---

## Step 5 — Add the Projects Section

```html
  <section id="projects">
    <h2>My Projects</h2>

    <article>
      <h3>Project 1: Personal Blog</h3>
      <p>A simple blog built with HTML and CSS.</p>
      <a href="https://github.com/alexrivera/blog" target="_blank" rel="noopener noreferrer">View on GitHub</a>
    </article>

    <article>
      <h3>Project 2: Recipe App</h3>
      <p>A recipe collection app with search functionality.</p>
      <a href="https://alexrivera.github.io/recipes" target="_blank" rel="noopener noreferrer">Live Demo</a>
      —
      <a href="recipe-app.zip" download="recipe-app-source.zip">Download Source Code</a>
    </article>
  </section>
```

**What the `download` attribute does:** Instead of opening the file, the browser downloads it. You can optionally give it a custom filename.

---

## Step 6 — Add the Contact Section

```html
  <section id="contact">
    <h2>Get In Touch</h2>
    <p>I am always open to new opportunities and collaborations.</p>

    <ul>
      <li>Email: <a href="mailto:alex@example.com">alex@example.com</a></li>
      <li>Phone: <a href="tel:+15551234567">(555) 123-4567</a></li>
      <li>GitHub: <a href="https://github.com/alexrivera" target="_blank" rel="noopener noreferrer">github.com/alexrivera</a></li>
      <li>LinkedIn: <a href="https://linkedin.com/in/alexrivera" target="_blank" rel="noopener noreferrer">linkedin.com/in/alexrivera</a></li>
    </ul>

    <p><a href="#home">Back to top</a></p>
  </section>

</main>
```

**What each link type does:**
- `mailto:` — opens the user's email client with a new message
- `tel:` — on mobile, opens the phone dialer

---

## Step 7 — Add a Footer

```html
<footer>
  <p>Built with HTML by Alex Rivera — 2025</p>
</footer>
```

---

## Step 8 — Test All Links

Go through each link and verify:

- [ ] Nav links jump to the correct section on the page
- [ ] "Learn More About Me" jumps to the About section
- [ ] GitHub links open in a new tab
- [ ] Email link opens your email client
- [ ] Phone link works (especially on mobile)
- [ ] "Back to top" jumps back to the Home section
- [ ] Download link triggers a download (or shows 404 — that is fine)

---

## Checklist

- [ ] Navigation uses `<nav>` and `<ul>/<li>` structure
- [ ] All nav links use `href="#section-id"` format
- [ ] All sections have matching `id` attributes
- [ ] External links have `target="_blank"` and `rel="noopener noreferrer"`
- [ ] Email link uses `mailto:` protocol
- [ ] Phone link uses `tel:` protocol
- [ ] At least one `download` attribute link
- [ ] "Back to top" link present
- [ ] `<main>` wraps the main content
- [ ] `<footer>` at the bottom

---

## Bonus Challenges

1. Add a `<meta name="description">` to the head
2. Add `aria-label="Main navigation"` to the `<nav>` element
3. Add a `title` attribute to the external links: `title="Opens in a new tab"`
4. Add an SMS link: `<a href="sms:+15551234567">Text me</a>`
5. Add `aria-current="page"` to the active nav link
