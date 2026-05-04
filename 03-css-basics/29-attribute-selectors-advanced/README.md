# 29 — Attribute Selectors (Advanced)

## What Is This Lesson About?

Attribute selectors let you target elements based on their HTML attributes and attribute values — without adding extra classes.

---

## Basic Attribute Selectors

```css
/* Has the attribute */
[disabled] { opacity: 0.5; }
[required] { border-left: 3px solid orange; }

/* Exact value */
[type="email"] { }
[lang="en"] { }

/* Contains word */
[class~="btn"] { }

/* Starts with */
[href^="https"] { }
[href^="mailto"] { }

/* Ends with */
[href$=".pdf"] { }
[href$=".png"] { }

/* Contains substring */
[href*="github"] { }
[class*="icon-"] { }

/* Starts with value or value- */
[lang|="en"] { }  /* matches en, en-US, en-GB */
```

---

## Case-Insensitive Matching

```css
[type="email" i] { }  /* matches EMAIL, Email, email */
```

---

## Real-World Examples

```css
/* Style external links */
a[href^="http"]:not([href*="mysite.com"]) {
  color: #3498db;
}

a[href^="http"]:not([href*="mysite.com"])::after {
  content: ' ↗';
  font-size: 0.8em;
}

/* Style PDF links */
a[href$=".pdf"]::before {
  content: '📄 ';
}

/* Style required inputs */
input[required] {
  border-left: 3px solid #f39c12;
}

/* Style disabled elements */
[disabled] {
  opacity: 0.5;
  cursor: not-allowed;
}

/* Style data attributes */
[data-theme="dark"] { background: #0f172a; }
[data-size="large"] { font-size: 1.5rem; }
```
