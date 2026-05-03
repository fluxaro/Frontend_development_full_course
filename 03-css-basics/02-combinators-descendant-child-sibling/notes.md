# Notes — CSS Combinators

## Quick Reference

```css
/* Descendant (space): any depth */
nav a { }

/* Child (>): direct children only */
ul > li { }

/* Adjacent sibling (+): immediately after */
h2 + p { }

/* General sibling (~): all after */
h2 ~ p { }
```

## When to Use Each

| Combinator | Use When |
|---|---|
| Descendant | Styling all links in a nav, all paragraphs in an article |
| Child | Styling only direct list items, avoiding nested elements |
| Adjacent sibling | Removing margin from first paragraph after heading |
| General sibling | Styling all content after a specific element |

## Common Patterns

```css
/* Navigation links */
nav a { color: white; text-decoration: none; }

/* Direct list items only */
.menu > li { display: inline-block; }

/* Lead paragraph (first p after h1) */
h1 + p { font-size: 1.2rem; color: #666; }

/* All paragraphs after a blockquote */
blockquote ~ p { font-style: italic; }

/* Checked checkbox label */
input[type="checkbox"]:checked + label { font-weight: bold; }
```

## Common Mistakes

- Using descendant when you need child (accidentally styling nested elements)
- Forgetting that `+` only selects the IMMEDIATELY next sibling
- Using `~` when you only want the first sibling (use `+` instead)
- Over-nesting: `nav ul li a` — too specific, hard to override
