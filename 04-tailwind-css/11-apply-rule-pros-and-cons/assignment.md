# Assignment — Refactor a Utility-Heavy Page

## What You Are Building

You'll start with a page that has long, repeated utility strings in the HTML, then refactor it to extract repeated patterns — demonstrating the concept of `@apply` using a `<style>` block (since we're using the CDN).

---

## Requirements

Create `refactored-components.html` with the Tailwind CDN.

### Part 1 — The "Before" Version

Build a page with these repeated components, written with full utility strings in the HTML:

- [ ] At least 4 buttons of the same style (e.g., 4 primary buttons with identical classes)
- [ ] At least 3 cards with identical structure and classes
- [ ] At least 2 form inputs with identical classes
- [ ] A badge/tag component used at least 4 times

### Part 2 — The "After" Version (Refactored)

On the same page (or a second section), show the refactored version:

- [ ] Extract the button styles into a `.btn` and `.btn-primary` class in a `<style>` block
- [ ] Extract the card styles into a `.card` class
- [ ] Extract the input styles into an `.input` class
- [ ] Extract the badge styles into a `.badge` class
- [ ] The HTML should now use short class names like `class="btn btn-primary"` instead of the full utility string

### Part 3 — Explanation

- [ ] Add a comment in the `<style>` block explaining: "In a real project with a build step, these would use @apply. With CDN, we write the CSS values manually."
- [ ] Add a visible note on the page explaining the CDN limitation

---

## What Good Looks Like

- The "before" and "after" sections look identical visually
- The "after" HTML is significantly shorter and cleaner
- The `<style>` block is well-organized with comments
- The page includes a clear explanation of the CDN limitation

---

## Submission

Submit `refactored-components.html`. The page should show both the "before" (utility-heavy) and "after" (extracted classes) versions side by side or in separate sections.
