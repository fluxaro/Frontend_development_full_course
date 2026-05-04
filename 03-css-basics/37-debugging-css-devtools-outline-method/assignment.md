# Assignment — Debug and Fix a Broken Page

## What You Are Doing

You will receive a broken CSS page, identify all the bugs, and fix them.

---

## The Broken Page

Create `broken-page.html` and `broken-page.css` with these intentional bugs:

### Bug 1: Missing box-sizing
Cards overflow their container because padding is added to the width.

### Bug 2: Image gap
Images have a gap below them because they are inline elements.

### Bug 3: z-index not working
A badge does not appear above the card because the element is not positioned.

### Bug 4: Margin collapse
Two sections have unexpected spacing because vertical margins collapse.

### Bug 5: Flexbox on wrong element
A flex layout is not working because `display: flex` is on the child instead of the parent.

---

## Requirements

1. Create the broken page with all 5 bugs
2. Use the outline method to identify the issues
3. Use DevTools to inspect computed styles
4. Fix all 5 bugs
5. Document each bug and fix in a `debug-notes.md` file

---

## debug-notes.md Format

```markdown
## Bug 1: [Name]
**Symptom:** What you see
**Cause:** Why it happens
**Fix:** What you changed
```

---

## Submission

Submit `broken-page.html`, `broken-page.css`, `fixed-page.html`, `fixed-page.css`, and `debug-notes.md`.
