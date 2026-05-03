# Notes — Document Structure

## Document Structure Cheat Sheet

```html
<!DOCTYPE html>                          <!-- Line 1: Always -->
<html lang="en">                         <!-- Root element -->
  <head>                                 <!-- Metadata (not visible) -->
    <meta charset="UTF-8">              <!-- Character encoding -->
    <meta name="viewport"               <!-- Mobile responsiveness -->
          content="width=device-width, 
                   initial-scale=1.0">
    <title>Page Title</title>           <!-- Browser tab + SEO -->
    <meta name="description"            <!-- SEO snippet -->
          content="Page description.">
    <meta name="author"                 <!-- Optional: author -->
          content="Your Name">
    <link rel="stylesheet"              <!-- External CSS -->
          href="style.css">
    <link rel="icon"                    <!-- Favicon -->
          href="favicon.ico">
  </head>
  <body>                                 <!-- All visible content -->
    <!-- Your page content here -->
  </body>
</html>
```

---

## What Each Tag Does

| Tag | Location | Purpose |
|-----|----------|---------|
| `<!DOCTYPE html>` | Line 1 | Declares HTML5 document type |
| `<html lang="en">` | Root | Root element; `lang` sets page language |
| `<head>` | Inside `<html>` | Container for metadata |
| `<meta charset="UTF-8">` | Inside `<head>` | Sets character encoding |
| `<meta name="viewport">` | Inside `<head>` | Controls mobile viewport |
| `<title>` | Inside `<head>` | Browser tab title + SEO title |
| `<meta name="description">` | Inside `<head>` | SEO description snippet |
| `<link rel="stylesheet">` | Inside `<head>` | Links external CSS file |
| `<body>` | Inside `<html>` | All visible page content |

---

## The Viewport Meta Tag Explained

```html
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```

Breaking down the `content` value:

| Value | Meaning |
|-------|---------|
| `width=device-width` | Page width = device screen width |
| `initial-scale=1.0` | No zoom on initial load |

**Without this tag:** Mobile browsers render the page at ~980px wide and zoom out, making text tiny.  
**With this tag:** Mobile browsers use the actual device width, making the page readable.

---

## Language Codes

```html
<html lang="en">    <!-- English -->
<html lang="es">    <!-- Spanish -->
<html lang="fr">    <!-- French -->
<html lang="de">    <!-- German -->
<html lang="pt">    <!-- Portuguese -->
<html lang="ja">    <!-- Japanese -->
<html lang="zh">    <!-- Chinese -->
<html lang="ar">    <!-- Arabic -->
<html lang="ko">    <!-- Korean -->
```

For regional variants:
```html
<html lang="en-US">   <!-- American English -->
<html lang="en-GB">   <!-- British English -->
<html lang="pt-BR">   <!-- Brazilian Portuguese -->
<html lang="zh-CN">   <!-- Simplified Chinese -->
```

---

## Common Mistakes with Document Structure

### ❌ Missing DOCTYPE
```html
<!-- Wrong — no DOCTYPE -->
<html lang="en">
  <head>...</head>
  <body>...</body>
</html>

<!-- Correct -->
<!DOCTYPE html>
<html lang="en">
  <head>...</head>
  <body>...</body>
</html>
```

### ❌ Content outside body
```html
<!-- Wrong -->
<html>
  <head>...</head>
  <body>...</body>
  <p>This is outside body!</p>  <!-- ❌ -->
</html>

<!-- Correct -->
<html>
  <head>...</head>
  <body>
    <p>This is inside body.</p>  <!-- ✅ -->
  </body>
</html>
```

### ❌ Title in body instead of head
```html
<!-- Wrong -->
<body>
  <title>My Page</title>  <!-- ❌ title belongs in head -->
  <h1>Hello</h1>
</body>

<!-- Correct -->
<head>
  <title>My Page</title>  <!-- ✅ -->
</head>
<body>
  <h1>Hello</h1>
</body>
```

### ❌ Missing charset (causes encoding issues)
```html
<!-- Wrong — may show garbled characters -->
<head>
  <title>My Page</title>
</head>

<!-- Correct — charset should be first in head -->
<head>
  <meta charset="UTF-8">  <!-- ✅ first! -->
  <title>My Page</title>
</head>
```

### ❌ Missing lang attribute
```html
<!-- Wrong — accessibility and SEO issue -->
<html>

<!-- Correct -->
<html lang="en">
```

---

## Head Section: Order Matters

The recommended order for elements in `<head>`:

1. `<meta charset>` — **must be first** (within first 1024 bytes)
2. `<meta name="viewport">`
3. `<title>`
4. Other `<meta>` tags
5. `<link>` tags (CSS, favicon)
6. `<script>` tags (if in head)

---

## The `<title>` Tag Best Practices

```html
<!-- Too vague -->
<title>Home</title>

<!-- Too long (over 60 chars gets cut off in Google) -->
<title>Welcome to My Amazing Personal Website About Everything I Love</title>

<!-- Just right — descriptive, under 60 chars -->
<title>Alex Rivera — Frontend Developer Portfolio</title>
<title>The Dark Knight (2008) — Movie Review</title>
<title>Contact Us — Acme Corporation</title>
```

**Format:** `Page Name — Site Name` or `Page Name | Site Name`

---

## Checking Your Structure

Quick mental checklist before saving:

1. ✅ `<!DOCTYPE html>` on line 1?
2. ✅ `<html lang="...">` wraps everything?
3. ✅ `<head>` has charset, viewport, title?
4. ✅ All visible content inside `<body>`?
5. ✅ All tags properly closed and nested?
6. ✅ Consistent indentation (2 spaces)?
