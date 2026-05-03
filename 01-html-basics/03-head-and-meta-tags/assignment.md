# Assignment — Complete Head Section Page

## What You Are Building

Create an HTML page with a fully populated `<head>` section. The page content should be a short article or blog post on any topic you choose.

No CSS file required. No JavaScript. Focus entirely on the `<head>` section.

---

## Requirements

### Head Section

Your `<head>` must include ALL of the following:

**Basic Meta Tags:**
- `<meta charset="UTF-8">` — must be the first element in head
- `<meta name="viewport" content="width=device-width, initial-scale=1.0">`
- `<title>` — descriptive, 50–60 characters, includes the topic and a site name
- `<meta name="description">` — 150–160 characters, a compelling description
- `<meta name="author">` — your name

**Open Graph Tags (all 5 required):**
- `<meta property="og:title">`
- `<meta property="og:description">`
- `<meta property="og:image">` — use a real image URL from Unsplash or similar
- `<meta property="og:url">`
- `<meta property="og:type">` — use "website" or "article"

**Twitter Card:**
- `<meta name="twitter:card" content="summary_large_image">`

**Links:**
- `<link rel="icon">` — a favicon (the emoji SVG trick is fine)
- `<link rel="stylesheet" href="style.css">` — even if the file does not exist
- `<link rel="canonical">` — with a proper URL

### Body Content

Your page must have meaningful content that matches what your meta tags describe:
- At least one `<h1>` heading
- At least 2 `<h2>` sections
- At least 3 paragraphs of real content

---

## Topic Ideas

Pick any topic you are interested in:
- A how-to guide (how to make coffee, how to learn guitar)
- A review (book, movie, game, restaurant)
- A list article (top 5 things I learned this week)
- A personal story or experience

---

## What Good Looks Like

- Every required tag is present and has a real, meaningful value
- The `title` and `og:title` are slightly different (title includes site name, og:title is just the article title)
- The `description` and `og:description` are compelling and the right length
- The favicon is visible in the browser tab
- The body content matches what the meta tags describe
- The page passes W3C validation at `https://validator.w3.org/`

---

## Bonus Challenges

- Add `<meta property="article:published_time">` with today's date in ISO format
- Add `<meta property="article:author">` with your name
- Add `<meta name="robots" content="index, follow">`
- Research what `<meta http-equiv="X-UA-Compatible" content="IE=edge">` does and add it

---

## Submission

Save as `my-article.html` and submit via GitHub or file upload.
