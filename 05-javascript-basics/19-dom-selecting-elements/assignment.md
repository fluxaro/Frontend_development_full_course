# Assignment — DOM Explorer

## What You Are Building

An interactive DOM explorer that lets users select elements on the page using different methods and highlights the results, demonstrating all selection techniques.

---

## Requirements

Create `dom-explorer.html` with a rich HTML structure containing:
- A navbar with links
- A hero section with a heading and paragraph
- A grid of 6 cards, each with a title, description, and a button
- A form with various input types
- A footer

### Part 1 — Selection Methods Demo

Build a control panel with buttons that demonstrate each selection method:

- `getElementById('hero')` — highlight the hero section
- `querySelector('h1')` — highlight the first h1
- `querySelectorAll('.card')` — highlight all cards
- `querySelector('input[type="email"]')` — highlight the email input
- `querySelectorAll('a')` — highlight all links
- `querySelector('.card:nth-child(3)')` — highlight the 3rd card

When a button is clicked:
- Add a yellow highlight border to the selected element(s)
- Show the count of matched elements
- Show the element's tag name, id, and classes

### Part 2 — DOM Tree Inspector

Click any element on the page to inspect it:
- Show its tag name
- Show its id (if any)
- Show its class list
- Show its parent element's tag name
- Show its children count
- Show its text content (first 50 chars)

### Part 3 — Traversal Demo

A "Traverse" section that shows:
- Starting from a card, navigate to its parent
- Starting from a card, navigate to its siblings
- Starting from the body, navigate to `firstElementChild` and `lastElementChild`
- Use `closest()` to find the nearest `.container` ancestor

### Part 4 — NodeList vs Array

Show a demo where:
- `querySelectorAll('.card')` returns a NodeList
- Convert it to an array with `Array.from()`
- Apply `filter()` to get only cards with a specific class
- Show the difference in available methods

---

## What Good Looks Like

- Clicking selection buttons visually highlights the matched elements
- The inspector shows accurate information about clicked elements
- Traversal demo shows the correct parent/sibling/child relationships
- NodeList vs Array difference is clearly demonstrated

---

## Submission

Submit `dom-explorer.html`.
