# Assignment — Theme Switcher and Live Editor

## What You Are Building

An interactive page with a live text editor and a theme switcher, demonstrating DOM manipulation through `textContent`, `classList`, `setAttribute`, and `style`.

---

## Requirements

Create `dom-manipulation-app.html` with:

### Part 1 — Live Profile Editor

A form on the left and a profile card preview on the right that updates in real time:

Form fields:
- Name (text input)
- Role (text input)
- Bio (textarea)
- Avatar colour (colour picker)
- Skills (comma-separated text input)

Profile card preview:
- Avatar circle with initials (first letter of first and last name)
- Avatar background colour from the colour picker
- Name, role, bio displayed
- Skills as coloured tags

All updates happen in real time using `input` events and `textContent`/`classList`.

### Part 2 — Theme Switcher

Three theme buttons: Light, Dark, Ocean.

Each theme changes:
- Body background colour
- Text colour
- Card background colour
- Border colour

Use `classList` to add/remove theme classes on the `<body>` element. Define the themes in CSS.

### Part 3 — Card State Manager

A grid of 4 cards. Each card has:
- A "Toggle Active" button — adds/removes `.active` class (changes border colour)
- A "Toggle Featured" button — adds/removes `.featured` class (changes background)
- A "Disable" button — adds `disabled` attribute and dims the card
- A status badge that shows the current state

### Part 4 — Data Attributes

A list of items where each item has `data-id`, `data-category`, and `data-priority` attributes.

- Clicking an item shows its data attributes in an inspector panel
- A filter by category using `querySelectorAll('[data-category="..."]')`
- A sort by priority using `dataset.priority`

---

## What Good Looks Like

- Profile card updates instantly as the user types
- Theme switching is smooth (add CSS transitions)
- Card states are visually distinct
- Data attribute inspector shows all attributes correctly

---

## Submission

Submit `dom-manipulation-app.html`.
