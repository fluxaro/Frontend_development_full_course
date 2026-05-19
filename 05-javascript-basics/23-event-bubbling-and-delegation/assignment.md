# Assignment — Dynamic List with Event Delegation

## What You Are Building

A dynamic task management list that uses event delegation to handle all interactions with a single listener — including items added dynamically after the page loads.

---

## Requirements

Create `event-delegation-app.html` with:

### Part 1 — Bubbling Visualiser

A nested set of boxes (outer → middle → inner) that visually shows event bubbling:
- Clicking any box highlights the path the event travels
- Show which elements fired in order
- A "Stop Propagation" toggle that stops bubbling at the middle box

### Part 2 — Dynamic Task List (event delegation)

A task list where ALL interactions are handled by ONE listener on the `<ul>`:

Each task item has:
- A checkbox to mark complete
- The task text
- A priority badge (High/Medium/Low)
- An "Edit" button (inline editing)
- A "Delete" button

New tasks can be added dynamically. The delegation listener must handle tasks added after the page loads.

### Part 3 — Accordion (delegation)

A FAQ accordion with 5 questions. Use ONE listener on the container to handle all expand/collapse interactions.

### Part 4 — Image Gallery (delegation)

A grid of 8 image placeholders. Use ONE listener on the grid to:
- Show a larger preview when an image is clicked
- Add a "selected" border to the clicked image
- Remove selection from previously selected image

### Part 5 — e.target vs e.currentTarget Demo

A visual demo showing the difference:
- A container with 3 buttons
- One listener on the container
- Show both `e.target` and `e.currentTarget` when any button is clicked

---

## What Good Looks Like

- The bubbling visualiser clearly shows the propagation path
- The task list works correctly for dynamically added tasks
- All interactions use delegation (one listener per section)
- `e.target.closest()` is used to find the right ancestor

---

## Submission

Submit `event-delegation-app.html`.
