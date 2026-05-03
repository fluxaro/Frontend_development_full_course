# Class Work — Build a Properly Structured HTML Document

## What You Will Build

A complete, valid HTML document about your favorite movie. You will type every part of the structure yourself and understand what each line does.

**Time:** 35 minutes  
**Tools:** VS Code and a browser

---

## Step 1 — Start From Nothing

Create a new file called `movie-page.html`. Do not use the `!` shortcut yet — type everything manually so it sticks.

### Type the DOCTYPE

```html
<!DOCTYPE html>
```

Save. Open in browser. You will see a blank page — that is correct.

**Why:** The browser needs this declaration before anything else. It tells the browser you are using HTML5.

---

## Step 2 — Add the Root Element

```html
<!DOCTYPE html>
<html lang="en">

</html>
```

**Why `lang="en"`:** Try changing it to `lang="fr"` — Chrome may offer to translate the page. The `lang` attribute tells browsers and screen readers what language the content is in.

---

## Step 3 — Add the Head Section

```html
<!DOCTYPE html>
<html lang="en">
  <head>

  </head>
</html>
```

The `<head>` is empty for now. Save and refresh — still blank. That is expected. The head contains information about the page, not visible content.

---

## Step 4 — Add Character Encoding

```html
<head>
  <meta charset="UTF-8">
</head>
```

**Test it:** Add a paragraph in the body with special characters: `<p>Café, naïve, résumé</p>`. Without `charset="UTF-8"`, these might show as garbled characters. With it, they display correctly.

---

## Step 5 — Add the Viewport Meta Tag

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
</head>
```

**Why:** Without this, mobile browsers zoom out to show the full desktop version of your page. This tag tells mobile browsers to use the device's actual width.

---

## Step 6 — Add the Title

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Dark Knight — Movie Review</title>
</head>
```

Save and look at your browser tab. You should see "The Dark Knight — Movie Review". This is also what appears in Google search results.

---

## Step 7 — Add a Meta Description

```html
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>The Dark Knight — Movie Review</title>
  <meta name="description" content="A review of The Dark Knight (2008), Christopher Nolan's masterpiece of superhero cinema.">
</head>
```

**Why:** This text appears under your page title in Google search results. It does not affect ranking directly, but it affects whether people click your link.

---

## Step 8 — Add the Body

```html
<body>

</body>
```

---

## Step 9 — Add Content to the Body

Now build out the full page inside `<body>`:

```html
<body>
  <h1>The Dark Knight (2008)</h1>

  <h2>Overview</h2>
  <p>
    Directed by Christopher Nolan, The Dark Knight is widely considered one of the greatest
    superhero films ever made. Released in 2008, it stars Christian Bale as Batman and
    Heath Ledger in his iconic, Oscar-winning role as the Joker.
  </p>

  <h2>Plot Summary</h2>
  <p>
    Batman, Lieutenant James Gordon, and District Attorney Harvey Dent form an alliance
    to dismantle organized crime in Gotham City. But their efforts are disrupted by the
    Joker, a criminal mastermind who seeks to create chaos and expose the dark side of
    Gotham's heroes.
  </p>

  <h2>Why I Love This Film</h2>
  <p>
    The Dark Knight transcends the superhero genre. It is a crime thriller, a philosophical
    exploration of chaos versus order, and a character study all in one.
  </p>

  <h2>My Rating</h2>
  <p>10 out of 10</p>
</body>
```

---

## Step 10 — Validate Your HTML

1. Go to `https://validator.w3.org/#validate_by_input`
2. Copy your entire HTML and paste it in
3. Click "Check"
4. Fix any errors or warnings

**Common errors to look for:**
- Missing `<!DOCTYPE html>`
- Missing `lang` attribute on `<html>`
- Missing `charset` meta tag
- Unclosed tags

---

## Checklist

- [ ] `<!DOCTYPE html>` on line 1
- [ ] `<html lang="en">` wraps everything
- [ ] `<head>` contains `charset`, `viewport`, `title`, and `description`
- [ ] `<body>` contains all visible content
- [ ] Page title shows in browser tab
- [ ] Content is properly indented
- [ ] HTML passes W3C validation with 0 errors

---

## Bonus Challenges

1. Add a `<nav>` element with links to each section using anchor links
2. Add a `<footer>` at the bottom with your name and the date
3. Add a `<header>` element wrapping the `<h1>`
4. Add `<main>` wrapping all the main content sections
