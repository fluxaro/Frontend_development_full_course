# Class Work — Your First HTML File

## What You Will Build

By the end of this exercise you will have a real HTML file that opens in a browser and shows content. You will type every line yourself so it sticks in your memory.

**Time:** 30 minutes  
**Tools:** VS Code (or any text editor) and a web browser

---

## Step 1 — Create Your File

1. Open VS Code
2. Go to File → New File
3. Save it immediately as `my-first-page.html` on your Desktop

The `.html` extension is what tells your computer this is a webpage file.

---

## Step 2 — Type the DOCTYPE Declaration

Type this as the very first line:

```html
<!DOCTYPE html>
```

**What this does:** It tells the browser "this is an HTML5 document." Without it, browsers go into quirks mode and may display things incorrectly. Always put it on line 1.

Save the file. Open it in your browser. You will see a blank white page — that is correct.

---

## Step 3 — Add the Root HTML Element

```html
<!DOCTYPE html>
<html lang="en">

</html>
```

**What this does:** The `<html>` tag wraps everything on the page. The `lang="en"` attribute tells browsers and screen readers the page is in English. This matters for accessibility.

---

## Step 4 — Add the Head Section

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First Page</title>
  </head>
</html>
```

**What each line does:**
- `<head>` — contains information about the page, not visible content
- `<meta charset="UTF-8">` — makes sure special characters display correctly
- `<title>` — the text that appears in the browser tab

Save and refresh your browser. You should see "My First Page" in the tab.

---

## Step 5 — Add the Body Section

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First Page</title>
  </head>
  <body>

  </body>
</html>
```

**What this does:** The `<body>` tag is where all visible content goes. Everything the user sees on the page lives inside `<body>`.

---

## Step 6 — Add a Heading

Inside the `<body>`, type:

```html
<body>
  <h1>Welcome to My First Webpage!</h1>
</body>
```

Save and refresh. You should see a large bold heading on the page.

**What this does:** `<h1>` is the main heading — the most important title on the page. There should only be one `<h1>` per page.

---

## Step 7 — Add a Paragraph

```html
<body>
  <h1>Welcome to My First Webpage!</h1>
  <p>I am learning HTML and this is my very first webpage.</p>
</body>
```

Save and refresh. You should see the heading and a paragraph below it.

**What this does:** `<p>` creates a paragraph. The browser automatically adds space above and below it.

---

## Step 8 — Add a Subheading and More Content

```html
<h1>Welcome to My First Webpage!</h1>
<p>I am learning HTML and this is my very first webpage.</p>

<h2>About Me</h2>
<p>My name is Alex. I am learning web development and I am excited to build things for the internet.</p>
```

**What this does:** `<h2>` is a second-level heading — a subheading under the main `<h1>`.

---

## Step 9 — Add a List

```html
<h2>My Hobbies</h2>
<ul>
  <li>Reading books</li>
  <li>Playing video games</li>
  <li>Learning to code</li>
</ul>
```

**What this does:** `<ul>` creates an unordered (bulleted) list. Each `<li>` is one list item.

---

## Step 10 — Add a Link

```html
<h2>My Favorite Website</h2>
<p>When I need to look something up, I use:</p>
<a href="https://developer.mozilla.org">MDN Web Docs</a>
```

**What this does:**
- `<a>` creates a hyperlink (anchor tag)
- `href` is the URL the link points to
- The text between the tags is what the user clicks

---

## Your Complete File

Your finished file should look like this:

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>My First Page</title>
  </head>
  <body>
    <h1>Welcome to My First Webpage!</h1>
    <p>I am learning HTML and this is my very first webpage.</p>

    <h2>About Me</h2>
    <p>My name is Alex. I am learning web development.</p>

    <h2>My Hobbies</h2>
    <ul>
      <li>Reading books</li>
      <li>Playing video games</li>
      <li>Learning to code</li>
    </ul>

    <h2>My Favorite Website</h2>
    <p>When I need to look something up, I use:</p>
    <a href="https://developer.mozilla.org">MDN Web Docs</a>
  </body>
</html>
```

---

## How to Open in Browser

- Right-click the file → Open With → your browser
- Or drag the file into a browser window
- Or in VS Code: right-click → Open with Live Server (if you have the extension)

---

## Checklist

- [ ] File is saved with the `.html` extension
- [ ] `<!DOCTYPE html>` is on line 1
- [ ] `<html lang="en">` wraps everything
- [ ] `<head>` contains `<meta charset>` and `<title>`
- [ ] `<body>` contains all visible content
- [ ] Page shows a heading in the browser
- [ ] Page shows paragraphs in the browser
- [ ] List items appear as bullet points
- [ ] Link is clickable

---

## Bonus Challenges

1. Add a second paragraph with something interesting about yourself
2. Add an `<h3>` subheading under one of your `<h2>` sections
3. Change the `<title>` to your own name
4. Add a second link to another website you like
5. Add `target="_blank"` to your link so it opens in a new tab
